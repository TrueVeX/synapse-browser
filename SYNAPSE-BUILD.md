# Building SYNAPSE Browser

SYNAPSE Browser by HumanForm Studios (Revoori Ashwath Reddy) is built on the Firefox engine.
It is licensed under the Mozilla Public License 2.0, and the MPL-2.0 file headers must stay in place.

## Windows x64 on GitHub Actions
Go to Actions → "SYNAPSE Windows Build" → Run workflow, or run:

    gh workflow run synapse-windows-build.yml --repo TrueVeX/synapse-browser --ref dev

The build takes about 3–6 hours. Download the `synapse-browser-win64-zip` artifact; it is portable,
so run `synapse\synapse.exe`.

## Local build (16 GB+ RAM, 8+ cores, about 60 GB free)
    npm i
    npm run init
    python3 ./scripts/update_en_US_packs.py
    npm run build
    npm start

## SYNAPSE defaults
- Branding: `configs/branding/release` (logos), `surfer.json` (name, vendor, version)
- Low RAM: `prefs/zen/zen.yaml` sets 2 content processes, no preloading, early tab unloading and small caches
- Fewer animations: reduced motion, no Windows Mica blur, shorter transitions
