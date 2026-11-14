# Fish Tank Screen

A flat screen that turns into a deep fish tank. One HTML file. Raw WebGL2. No libraries, no image files, no 3D engine.

**Live page:** https://orchidstreet.github.io/fish-tank-screen/

Everything you see is built from maths when the page loads: the fish, the reef, the whale shark, the jellyfish and the glass.

## How to watch

Open the live page in a desktop browser and make it full screen. The film is 65 seconds and loops.

| Key | What it does |
| --- | --- |
| Space or click | Pause |
| Left and right arrows | Scrub 2 seconds (hold Shift for 10) |
| R | Restart |
| 1 to 4 | Quality: 1, 4, 8 or 16 samples per frame |

It needs WebGL2 with float render targets, and a reasonable graphics chip. If it runs slowly it reloads itself once at a smaller size.

## Why it looks deep

- The picture is drawn as if the screen were a window, with the view skewed to a moving eye point (off-axis projection).
- A picture frame at the screen plane gives the eye a fixed edge. When a fish crosses the frame, it reads as being in front of the screen.
- Water removes red light with distance, far things blur, and everything casts a shadow.

## How it was made

Every line was written by Claude (Claude Code, Fable 5.2), from plain-language prompts. Four set pieces were written by Opus subagents working to a written brief: the whale shark, the shattering glass, the coral reef and the glowing night.

The film version was rendered offline from this same file: 3,900 frames at 1080p and 60 frames per second, each frame the average of 64 renders with a different lens position, moment in time and light position. That gives true focus blur, motion blur and soft shadows. The page takes `?film=1`, `?stills=` and `?f=` for that render harness; without them it plays live.
