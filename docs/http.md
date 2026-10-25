# HTTP API

Base URL `https://movoa.ai`. Every call is a `POST` with `Authorization: Bearer sk-...` (create a key at [movoa.ai/settings/apikeys](https://movoa.ai/settings/apikeys)).

Every answer is JSON in one envelope: `{"code": 0, "message": "ok", "data": {...}}` on success. A refusal is a non-zero `code` (still HTTP 200), and `data.reason` says why. A wrong or deleted key is HTTP 401.

## 1. Submit a run

```bash
curl -s -X POST https://movoa.ai/api/ai/generate \
  -H "Authorization: Bearer $MOVOA_API_KEY" -H "content-type: application/json" \
  -d '{"provider":"auto","mediaType":"video","model":"minimax-h3","scene":"text-to-video",
       "prompt":"a paper boat drifting on a calm lake at sunrise, slow dolly in, soft water lapping",
       "options":{"duration":6,"resolution":"480p","aspect_ratio":"16:9","sound":true}}'
```

```json
{"code":0,"message":"ok","data":{"id":"<taskId>","status":"processing"}}
```

| Field | Value |
|---|---|
| `provider` | always `"auto"` (the server picks the channel) |
| `mediaType` | `"video"` |
| `model` | see [Models](models.md) |
| `scene` | `"text-to-video"`, or `"image-to-video"` with a photo |
| `prompt` | the shot: what happens, the camera, the sound |
| `options.image_input` | `["https://.../photo.jpg"]` for photo to video (one public https URL) |
| `options.duration` / `resolution` / `aspect_ratio` | per model, see [Models](models.md) |
| `options.sound` | `true` |

## 2. Poll the run

```bash
curl -s -X POST https://movoa.ai/api/ai/query \
  -H "Authorization: Bearer $MOVOA_API_KEY" -H "content-type: application/json" \
  -d '{"taskId":"<taskId>"}'
```

`data.status` is `pending` or `processing` while it runs (with `queued: true` and `queueEta` in seconds when it is waiting its turn), then `success` with `data.videos: ["https://..."]`, or `failed` with `data.errorMessage`. Poll every 10 seconds; a run takes minutes.

## 3. Credit balance

```bash
curl -s -X POST https://movoa.ai/api/user/get-user-credits -H "Authorization: Bearer $MOVOA_API_KEY"
# {"code":0,"data":{"remainingCredits":120,...}}
```

## Refusals

| Answer | Meaning |
|---|---|
| HTTP 401 | wrong or deleted key |
| `data.reason: "insufficient_credits"` | not enough credits ([pricing](https://movoa.ai/pricing)) |
| `data.reason: "plan_required"` | this model or quality needs a plan |
| `data.reason: "concurrency"` | your plan's parallel-run limit is reached; wait for a run to finish |
| `code: -2` / `code: -3` | the prompt or photo was refused by moderation / a short cooldown after repeated refusals |
| other `code: -1` | the `message` says what to fix |
