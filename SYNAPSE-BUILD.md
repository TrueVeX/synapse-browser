# SYNAPSE Browser

SYNAPSE Browser is made by HumanForm Studios (Revoori Ashwath Reddy). It is a rebranded build of
[Zen Browser](https://github.com/zen-browser/desktop), which is itself built on Mozilla Firefox.
The source is under the Mozilla Public License 2.0 (see `LICENSE`), and every MPL-2.0 header has been kept.
"Zen" and "Firefox" are the names of the upstream projects. SYNAPSE Browser uses its own name and logo.

## What changed from Zen
- `surfer.json`: name "SYNAPSE Browser", vendor "HumanForm Studios", binary `synapse.exe`, version 1.0.0.
- `configs/branding/release/`: SYNAPSE logos and icons, made from the SYNAPSE app icon.
- `configs/common/mozconfig`: app basename SYNAPSE, distribution id `com.humanformstudios.synapse`.
- `prefs/zen/theme.yaml`: black-and-white accent (`#ffffff`).
- en-US UI strings and the About dialog name SYNAPSE and HumanForm Studios, with credit to Zen and Firefox.
- The update host is `synapse-humanform.vercel.app`, so the browser never downloads Zen's updates.
  There are no SYNAPSE update packages yet, so update checks just fail quietly.

## Build (Windows x64, on GitHub Actions)
Actions tab → "SYNAPSE Windows Build" → Run workflow. You can also start it from a terminal:

    gh workflow run synapse-windows-build.yml --repo TrueVeX/synapse-browser --ref dev

The build takes about 3–6 hours on a free runner. When it finishes, the run's artifacts include
`synapse-browser-win64-zip` (a portable zip) and `synapse-browser-setup-exe` (an installer).

## Build locally (needs a strong PC: 16 GB+ RAM, 8+ cores, about 60 GB of free disk)
    npm i
    npm run init
    python3 ./scripts/update_en_US_packs.py
    npm run build
    npm start
