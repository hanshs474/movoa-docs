# Command line

```bash
docker run --rm -e MOVOA_API_KEY=sk-... san8888/movoa video "a paper boat drifting at sunrise, soft water lapping" --duration 6
docker run --rm -e MOVOA_API_KEY=sk-... san8888/movoa video "slow push in, she smiles" --image https://example.com/photo.jpg
docker run --rm -e MOVOA_API_KEY=sk-... san8888/movoa credits
```

On Linux: `sudo snap install movoa`. Flags: `--model`, `--image`, `--duration`, `--resolution`, `--aspect-ratio`, `--no-wait` (print the run id and exit), then `movoa status <id>`.

Source: [github.com/hanshs474/movoa-docker](https://github.com/hanshs474/movoa-docker).
