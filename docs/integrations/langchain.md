# LangChain

Generate video clips with sound from a LangChain agent via [langchain-movoa](https://pypi.org/project/langchain-movoa/).

## Install

```bash
pip install langchain-movoa
```

Set `MOVOA_API_KEY` from [movoa.ai/settings/apikeys](https://movoa.ai/settings/apikeys) or pass `api_key=`.

## Usage

```python
from langchain_movoa import MovoaVideoGenerator

tool = MovoaVideoGenerator()  # reads MOVOA_API_KEY
url = tool.invoke({
    "prompt": "a paper boat drifting down a rain gutter, low angle",
    "duration": 6,
})
```

To animate a photo as the first frame, pass `image_url` (a public https URL):

```python
url = tool.invoke({
    "prompt": "the camera slowly orbits the statue",
    "image_url": "https://example.com/statue.jpg",
})
```

Models: `minimax-h3` (default), `veo-3-1-fast`, `seedance-2-5`, `seedance-2`, `seedance-2-fast`, `seedance-2-mini`. Runs cost credits on your [Movoa](https://movoa.ai/) account at [movoa.ai/pricing](https://movoa.ai/pricing).

Source: [github.com/hanshs474/langchain-movoa](https://github.com/hanshs474/langchain-movoa).
