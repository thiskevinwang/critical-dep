# Error w/ `@swc/core`

This is a barebones repro for some errors seen from using

- next.config.js - `target: "serverless"`
- `@swc/core` in `getStaticProps`

## Steps

Run...

```bash
npm i
npm run build
```

see errors...

```console
Λ  npm run build

> build
> next build

warn  - The `target` config is deprecated and will be removed in a future version.
See more info here https://nextjs.org/docs/messages/deprecated-target-config
info  - Checking validity of types
info  - Creating an optimized production build
Failed to compile.

./node_modules/@swc/core-darwin-arm64/swc.darwin-arm64.node
Module parse failed: Unexpected character '�' (1:0)
You may need an appropriate loader to handle this file type, currently no loaders are configured to process this file. See https://webpack.js.org/concepts#loaders
(Source code omitted for this binary file)

Import trace for requested module:
./node_modules/@swc/core/binding.js
./node_modules/@swc/core/index.js
./pages/index.js
./node_modules/next/dist/build/webpack/loaders/next-serverless-loader/index.js?page=%2F&absolutePagePath=private-next-pages%2Findex.js&absoluteAppPath=private-next-pages%2F_app.js&absoluteDocumentPath=next%2Fdist%2Fpages%2F_document&absoluteErrorPath=next%2Fdist%2Fpages%2F_error&absolute404Path=&distDir=private-dot-next&buildId=JmVNe6U-5I794-fq-99iR&assetPrefix=&generateEtags=true&poweredByHeader=true&canonicalBase=&basePath=&runtimeConfig=&previewProps=%7B%22previewModeId%22%3A%227c966c6ac5bd418e1821d433e6fed70b%22%2C%22previewModeSigningKey%22%3A%22dc1fb0e2675a03a36e8fafc41b15dfe5abc180f20875f3ad8319f65efafbe541%22%2C%22previewModeEncryptionKey%22%3A%224759ddbc51d347fe23a07d713717aeeb1c4fe00e032bf2d550a7f4bacc74aafc%22%7D&loadedEnvFiles=W10%3D&i18n=!


> webpack config.resolve.alias was incorrectly overridden. https://nextjs.org/docs/messages/invalid-resolve-alias%
```
