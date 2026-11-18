# Haystack

Generate video clips with sound inside a Haystack pipeline via [movoa-haystack](https://pypi.org/project/movoa-haystack/).

## Install

```bash
pip install movoa-haystack
```

Set `MOVOA_API_KEY` from [movoa.ai/settings/apikeys](https://movoa.ai/settings/apikeys).

## Usage

```python
from movoa_haystack import MovoaVideoGenerator

gen = MovoaVideoGenerator(duration=6, aspect_ratio="16:9")
videos = gen.run(prompt="a paper boat drifting down a rain gutter, low angle")["videos"]
```

Source: [github.com/hanshs474/movoa-haystack](https://github.com/hanshs474/movoa-haystack) · [Movoa](https://movoa.ai/).
