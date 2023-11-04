# spline-selfhosted

- demo repository to show selfhosting of spline (vanillajs)
- goal: GDPR-compatibility (no 3rd party connections / cookies)

Used libraries:

- vite
- spline vanillajs runtime (https://www.npmjs.com/package/@splinetool/runtime)

Setup via:

```
npm install 
npm run dev
```

Spline offers several ways to export code, see: [Exporting as Code
](https://docs.spline.design/77c32288501a479fa8bc5e787f1e0878). There is also a Web Component available: 
[spline-viewer](https://viewer.spline.design/).

## How was this created?

We use the vanillajs runtime in this example.

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

Unzip it and place it into `public/3d-models`

3. Add `<canvas>` to index.html, add spline JS code to main.js

## Further goals

- [ ] transparent background
- [ ] Follow mouse cursor 
- [ ] Use click events --> Handling events outside of Spline (https://docs.spline.design/77c32288501a479fa8bc5e787f1e0878)
