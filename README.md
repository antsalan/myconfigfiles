# model-viewer: 3D model embed example

This repository contains a minimal example showing how to embed a 3D model in a web page using the <model-viewer> web component from Google (model-viewer).

## Overview

The snippet below demonstrates importing the `model-viewer` component as an ES module and using it to display a GLB model with AR support, environment lighting, and basic camera controls.

```html
<!-- Import the component -->
<script type="module" src="https://ajax.googleapis.com/ajax/libs/model-viewer/4.0.0/model-viewer.min.js"></script>

<!-- Use it like any other HTML element -->
<model-viewer
  alt="Neil Armstrong's Spacesuit from the Smithsonian Digitization Programs Office and National Air and Space Museum"
  src="shared-assets/models/NeilArmstrong.glb"
  ar
  environment-image="shared-assets/environments/moon_1k.hdr"
  poster="shared-assets/models/NeilArmstrong.webp"
  shadow-intensity="1"
  camera-controls
  touch-action="pan-y">
</model-viewer>
```

## Key attributes explained

- `alt`: Accessible description of the model for screen readers and fallback text.
- `src`: Path or URL to the `.glb` model file.
- `ar`: Enables AR features on supported devices (requires secure context / HTTPS on production).
- `environment-image`: HDR or environment map used for realistic lighting/reflections.
- `poster`: Image shown while the model is loading (or as a fallback on unsupported browsers).
- `shadow-intensity`: Controls the intensity of the model's shadow (0.0 - 1.0).
- `camera-controls`: Enables mouse/touch orbiting and zooming of the model.
- `touch-action`: Pointer/touch behavior hint (e.g., `pan-y`) to integrate with page scrolling.

## Quick setup / hosting notes

- The example imports `model-viewer` as an ES module. Serve files over a local or remote HTTP(S) server — opening the HTML file via `file://` may not work for module imports or fetching assets.
- GLB and HDR assets must be served with correct MIME types and allowed by CORS if hosted on a different origin.

Local dev example (PowerShell):

```powershell
# from the folder that contains your HTML and shared-assets directory
python -m http.server 8000
# then open http://localhost:8000/ in your browser
```

If you don't have Python, you can use other simple servers (Node.js `http-server`, live-server, etc.).

## Troubleshooting

- Blank model or errors in console: check the `src` path and verify the server is running and accessible.
- CORS errors when loading assets: ensure assets are served from the same origin or the remote server sends CORS headers.
- AR not working on desktop: AR typically works on supported mobile devices and when served over HTTPS or in a secure context.

## Resources

- Official docs: https://modelviewer.dev/
- Examples and API reference: https://modelviewer.dev/examples/

## License

No license specified. Add a license file (for example, `LICENSE` with the MIT license) if you want to make this project open-source.

---

If you'd like, I can:

- Add a tiny example HTML file wrapping this snippet (index.html).
- Add sample assets or point to a hosted sample GLB.
- Add a short badge and repository metadata.

Tell me which of those you'd like next.
