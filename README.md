# STD Visual Spec Editor

A browser-based editor for turning spatial scene ideas into structured, validated visual specifications.

[Open the live editor](https://kdeppaei.github.io/STD-Visual-Spec-Editor-Pages/)

## What it demonstrates

- Interactive scene and observer-view canvases for positioning objects and checking field of view.
- Structured object dimensions, relations, constraints, camera direction, and visibility rules.
- Director, storyboard, timeline, shot-list, and keyframe controls for cinematic planning.
- Deterministic validation before compiling prompts, negative prompts, STD JSON, YAML, and flow data.
- Multiple browser-local workspaces with JSON import/export and legacy-data migration.
- Traditional Chinese, Simplified Chinese, and English interface text.

## Engineering design

```text
Editor inputs
    -> normalized scene state
    -> structural validation
    -> scene and observer renderers
    -> prompt / JSON / YAML / shot-list compilers
    -> browser-local persistence and portable exports
```

The editor runs without a backend, account, analytics service, or external API. Project data stays in the browser unless the user explicitly exports it.

## Public artifact boundary

This repository is the public release and GitHub Pages deployment artifact. The distributable application is intentionally contained in [`index.html`](index.html), including its HTML, CSS, and JavaScript, so the published build remains portable and directly inspectable without a package installation or build step.

The single-file format is a delivery choice, not a claim that a monolithic file is the preferred development architecture. Future source-oriented releases can split state, validation, rendering, persistence, and compiler logic into testable modules while continuing to generate the standalone artifact.

## Run locally

Open `index.html` directly in a modern browser, or serve the repository when testing browser security boundaries:

```bash
python -m http.server 4173
```

Then open `http://localhost:4173`. This is a local development address; use the [public editor](https://kdeppaei.github.io/STD-Visual-Spec-Editor-Pages/) for the deployed version.

## Data and product boundaries

- Canvas markers represent positions and dimensions, not final generated artwork.
- Validation checks specification structure; it does not guarantee the output of an external image or video model.
- Browser storage is device-local and should be backed up through JSON export when the work matters.

## License

[MIT](LICENSE)
