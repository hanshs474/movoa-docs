# SDKs

Official clients for [Movoa](https://movoa.ai/?utm_source=readthedocs&utm_medium=docs), the AI video generator with sound. Every client has the same surface: `generate_video(prompt, model="minimax-h3", image_url=None, ...)` submits, waits and returns the video URL; `submit`, `status` and `credits` are there for finer control. All of them read `MOVOA_API_KEY` ([create a key](https://movoa.ai/settings/apikeys)).

| Language | Install | Source |
|---|---|---|
| Python | `pip install movoa` | [hanshs474/movoa-py](https://github.com/hanshs474/movoa-py) |
| JavaScript / TypeScript | `npm install movoa-ai` | [hanshs474/movoa-ts](https://github.com/hanshs474/movoa-ts) |
| Go | `go get github.com/hanshs474/movoa-go` | [hanshs474/movoa-go](https://github.com/hanshs474/movoa-go) |
| Rust | `cargo add movoa` | [hanshs474/movoa-rs](https://github.com/hanshs474/movoa-rs) |
| Ruby | `gem install movoa` | [hanshs474/movoa-rb](https://github.com/hanshs474/movoa-rb) |
| PHP | `composer require hanshs474/movoa` | [hanshs474/movoa-php](https://github.com/hanshs474/movoa-php) |
| Java / Kotlin | `io.github.hanshs474:movoa:0.1.0` | [hanshs474/movoa-java](https://github.com/hanshs474/movoa-java) |
| .NET | `dotnet add package Movoa` | [hanshs474/movoa-dotnet](https://github.com/hanshs474/movoa-dotnet) |
| Dart / Flutter | `dart pub add movoa` | [hanshs474/movoa-dart](https://github.com/hanshs474/movoa-dart) |
| Elixir | `{:movoa, "~> 0.1"}` | [hanshs474/movoa-ex](https://github.com/hanshs474/movoa-ex) |
| Swift | SwiftPM `https://github.com/hanshs474/movoa-swift` | [hanshs474/movoa-swift](https://github.com/hanshs474/movoa-swift) |
| Lua | `luarocks install movoa` | [hanshs474/movoa-lua](https://github.com/hanshs474/movoa-lua) |
| R | `install.packages("movoa", repos = "https://hanshs474.r-universe.dev")` | [hanshs474/movoa-r](https://github.com/hanshs474/movoa-r) |
| CLI (Docker / snap) | `docker run --rm -e MOVOA_API_KEY san8888/movoa video "..."` | [hanshs474/movoa-docker](https://github.com/hanshs474/movoa-docker) |

From an agent instead of code: the [MCP server](../integrations/mcp.md). Writing your own client: the [HTTP API](../http.md) is three calls.

Start with [text to video](https://movoa.ai/video/text-to-video); for [photo to video](https://movoa.ai/video/photo-to-video), pass a public photo URL as `image_url`.
