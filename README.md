# Interactive Diffusion Policy - Project Website

Project website for **Interactive Diffusion Policy: Safe Reactive Avoidance
through Proximity Sensing in Human-Robot Shared Environments**.

This repository contains the editable website and its selected figures and
videos. It does **not** contain robot-control software, training datasets,
checkpoints, the manuscript source, or internal correspondence.

## Local Preview

Python 3.10 or newer is sufficient. No package installation or build step is
required.

```sh
python tools/validate.py
python -m unittest discover -s tests -v
python tools/serve.py --port 8774
```

Open <http://127.0.0.1:8774/>. Stop the server with Ctrl+C. The preview serves
only `public/`, binds to loopback, and supports video seeking with HTTP ranges.
It does not serve the Git repository or development files.

## Editing

| File | Purpose |
| --- | --- |
| `public/index.html` | Page sections, text, figure captions, and result table |
| `public/style.css` | Responsive styling |
| `public/app.js` | Video chapters, comparison tabs, and media dialogs |
| `public/catalog.json` | Selected media metadata |
| `public/catalog.js` | The same catalog for direct-file and HTTP previews |
| `public/assets/` | Selected video, figure, and thumbnail files |
| `tools/validate.py` | Links, media integrity, and credential/path checks |
| `tools/update_catalog.py` | Refresh catalog integrity fields and cache revisions |
| `tools/serve.py` | Local-only static preview |

After editing the catalog or replacing media, run `python tools/update_catalog.py`
to synchronize `catalog.js` with `catalog.json`. It records actual web-file and
thumbnail hashes while preserving legacy source-image identifiers in `sha256`.
The validator checks catalog equality and web-file hashes. Re-run validation and
tests after making changes. JavaScript can additionally be checked with
`node --check public/app.js` when Node.js is available.

## Repository And Publication

This repository was created as a **private, save-only** copy of the selected
project page on 2026-10-27. No deployment workflow is installed and GitHub Pages
is not enabled. Repository privacy is not website access control: review the
hosting audience separately before any future deployment.

If publication is approved later, the static document root is `public/`.
All website resource paths are relative, so a repository subpath is supported.
The search-engine `noindex` directive is only a crawler hint, not authentication.

The source snapshot follows the supplied October 2026 manuscript. Its result
table is a transcription of the manuscript, not a new trial-level evaluation.
Media preserve the distinction between autonomous execution and human-assisted
data collection. Do not relabel one as the other.

The previous public paper-page route is being retired separately from this
repository. The personal research portfolio and robotics implementation
repositories are separate projects.

## Rights

No new license is granted by this migration. Paper figures, videos, institution
logos, and source code may have different rights; obtain the relevant owners'
approval before redistribution or applying a repository-wide license.
