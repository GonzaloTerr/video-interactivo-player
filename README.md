# video-interactivo-player

An interactive video player for the browser. It chains short clips together: at the end of each clip the viewer picks a button, and that choice decides which clip plays next. At the end, it can open WhatsApp with a message written from the path the viewer took.

I built it for the interactive video on my own website, so I wouldn't depend on a monthly subscription to a hosted tool. This repository has the player and a small example. My own video, character, voice and script are not included.

## Built with

Plain HTML, CSS and JavaScript, with no dependencies and no build step.

## Run it locally

The player loads `grafo.json`, so it needs a small local server:

```bash
npx serve .
```

Then open the address it shows. Add `?debug=1` to see the player's events on screen.

## Use your own video

1. Put your clips in `clips/`.
2. Describe the paths in `grafo.json`:
   - `inicio`: the first clip
   - `entradas`: other starting points, used with `?e=name` in the address
   - `nodos`: each clip, the question shown after it and its buttons
   - `salida`: the buttons on the last screen
   - `mensajes`: the WhatsApp message for each final choice
3. Add your WhatsApp numbers in `CONFIG`, at the top of `player.js`.

The code comments are in Spanish, because that's how I work on it.

## Analytics and privacy

The player doesn't ask for or store personal details. If [Umami](https://umami.is) is on the page, the player sends it each choice. If you set `CONFIG.WEBHOOK`, it also sends the path taken, without identifying the viewer.

## Plans

See [ROADMAP.md](ROADMAP.md).

## License

[MIT](LICENSE). The example clips are plain color placeholders that I generated with FFmpeg.
