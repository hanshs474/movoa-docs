# Vercel AI SDK

Generate video clips with sound using the Vercel AI SDK via [movoa-ai-provider](https://www.npmjs.com/package/movoa-ai-provider).

## Install

```bash
npm install movoa-ai-provider ai
```

Set `MOVOA_API_KEY` from [movoa.ai/settings/apikeys](https://movoa.ai/settings/apikeys).

## Usage

```ts
import { experimental_generateVideo as generateVideo } from 'ai';
import { movoa } from 'movoa-ai-provider';

const { video } = await generateVideo({
  model: movoa.video(),
  prompt: 'a paper boat drifting down a rain gutter, low angle',
});
```

Source: [github.com/hanshs474/movoa-ai-provider](https://github.com/hanshs474/movoa-ai-provider) · [Movoa](https://movoa.ai/).
