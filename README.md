# spline-selfhosted

- demo repository to show selfhosting of spline (vanillajs) without 3rd party connections

Demo: 

- https://spline-selfhosted.vercel.app/
- GDPR check: https://webbkoll.dataskydd.net/de/status?id=ba2a8f80-53c4-46ad-bfdf-d0e640e2bd68

Used libraries:

- vite
- spline vanillajs runtime (https://www.npmjs.com/package/@splinetool/runtime)

## Goals

- [x] GDPR-compatibility (no 3rd party connections / no cookies), checked with https://webbkoll.dataskydd.net/de/results?url=http%3A%2F%2Fspline-selfhosted.vercel.app%2F
- [ ] transparent background -> setBackgroundColor()?
- [ ] Follow mouse cursor 
- [ ] Use click events --> Handling events outside of Spline (https://docs.spline.design/77c32288501a479fa8bc5e787f1e0878), like here  https://2giomw.csb.app/
- [ ] Use preload? https://www.npmjs.com/package/@splinetool/runtime#preloading-your-scene

## Local setup

```
npm install 
npm run dev
```

## How was this created?

Spline offers several ways to export code, see: [Exporting as Code
](https://docs.spline.design/77c32288501a479fa8bc5e787f1e0878). There is also a Web Component available: 
[spline-viewer](https://viewer.spline.design/).

We use the vanillajs runtime (https://www.npmjs.com/package/@splinetool/runtime) in this example.

1. Scaffold vite project, install spline runtime (vanillajs)

```bash
# https://vitejs.dev/guide/#scaffolding-your-first-vite-project
npm create vite@latest . -- --template vanilla

# https://www.npmjs.com/package/@splinetool/runtime
npm install @splinetool/runtime
```

2. Export spline scene

Use "Download bundled zip (Web content)" here:

![screenshot spline export vanillajs dialog](screenshot_export_vanillajs.png)

Unzip it and place the `scene.splinecode` file into `public/3d-models`.

Instead of loading the scene from the spline server, we use the local file:

```
spline.load('/3d-models/planet/scene.splinecode');
```

3. Add `<canvas>` to index.html, add spline JS code to main.js

## Credits

- 3D Model example from spline: Planet (https://spline.design/examples)