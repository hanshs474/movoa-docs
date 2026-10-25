# Movoa API and SDKs

Unlimited AI video generator with sound: on paid plans the tenth take of a shot costs what the first did, and your first clip is free to make right now.

[Movoa](https://movoa.ai/?utm_source=readthedocs&utm_medium=docs) makes short video clips with sound from a sentence ([text to video](https://movoa.ai/video/text-to-video)) or from a photo ([photo to video](https://movoa.ai/video/photo-to-video)). These pages document the same engine for code and agents: one API key, three calls.

- **Key**: create one at [movoa.ai/settings/apikeys](https://movoa.ai/settings/apikeys) and send it as `Authorization: Bearer sk-...`.
- **Cost**: runs cost credits on your Movoa account, at the prices on [movoa.ai/pricing](https://movoa.ai/pricing).
- **Models**: MiniMax H3 (default), [Seedance 2.5](https://movoa.ai/video/seedance-2-5), [Veo 3](https://movoa.ai/video/google-veo-3) Fast, Seedance 2.0 / Fast / Mini. Every clip comes back as [AI video with audio](https://movoa.ai/video/ai-video-with-audio). See [Models and parameters](models.md).

## Pick a way in

| You are | Use |
|---|---|
| Writing code | an [SDK](sdk/README.md) (Python, JavaScript, Go, Rust, Ruby, PHP and more) or the [HTTP API](http.md) directly |
| In Claude, Cursor, Cline or Gemini CLI | the [MCP server](integrations/mcp.md): `npx -y movoa-mcp` or the hosted endpoint `https://movoa.ai/api/mcp` |
| In a terminal or CI | the [command line](integrations/cli.md): `docker run --rm -e MOVOA_API_KEY san8888/movoa video "..."` |
