# Error w/ `@swc/core`

This is a barebones repro for some errors seen from using

- next.config.js - `target: "serverless"`
- `@swc/core` in `getStaticProps`

I think the actual error is `Error: Can not load bindings`,
which originates from `@node-rs/helper/lib/loader.js - loadBinding`

## Steps

Run...

```bash
npm i
npm run build
```

see errors...

```console
✗  npm run build

> build
> next build

warn  - The `target` config is deprecated and will be removed in a future version.
See more info here https://nextjs.org/docs/messages/deprecated-target-config
info  - Checking validity of types
info  - Creating an optimized production build
warn  - Compiled with warnings

./node_modules/@node-rs/helper/lib/loader.js
Critical dependency: the request of a dependency is an expression

Import trace for requested module:
./node_modules/@node-rs/helper/lib/index.js
./node_modules/@swc/core/index.js
./pages/index.js
./node_modules/next/dist/build/webpack/loaders/next-serverless-loader/index.js?page=%2F&absolutePagePath=private-next-pages%2Findex.js&absoluteAppPath=private-next-pages%2F_app.js&absoluteDocumentPath=next%2Fdist%2Fpages%2F_document&absoluteErrorPath=next%2Fdist%2Fpages%2F_error&absolute404Path=&distDir=private-dot-next&buildId=F68DPEy1I2QGOb0HZBdlW&assetPrefix=&generateEtags=true&poweredByHeader=true&canonicalBase=&basePath=&runtimeConfig=&previewProps=%7B%22previewModeId%22%3A%224c311bacc47c8a7607930533d8c1f4cc%22%2C%22previewModeSigningKey%22%3A%222e3076d32e5c50bd18f737e4f78d3fcd3a3cd71a28e7d77797b4c2a0f0fb0998%22%2C%22previewModeEncryptionKey%22%3A%22aa7e494e4be8ad545d3b89401130f0cddd5cc7fad559dc5ccdc523d783aae4f3%22%7D&loadedEnvFiles=W10%3D&i18n=!

./node_modules/@node-rs/helper/lib/loader.js
Critical dependency: require function is used in a way in which dependencies cannot be statically extracted

Import trace for requested module:
./node_modules/@node-rs/helper/lib/index.js
./node_modules/@swc/core/index.js
./pages/index.js
./node_modules/next/dist/build/webpack/loaders/next-serverless-loader/index.js?page=%2F&absolutePagePath=private-next-pages%2Findex.js&absoluteAppPath=private-next-pages%2F_app.js&absoluteDocumentPath=next%2Fdist%2Fpages%2F_document&absoluteErrorPath=next%2Fdist%2Fpages%2F_error&absolute404Path=&distDir=private-dot-next&buildId=F68DPEy1I2QGOb0HZBdlW&assetPrefix=&generateEtags=true&poweredByHeader=true&canonicalBase=&basePath=&runtimeConfig=&previewProps=%7B%22previewModeId%22%3A%224c311bacc47c8a7607930533d8c1f4cc%22%2C%22previewModeSigningKey%22%3A%222e3076d32e5c50bd18f737e4f78d3fcd3a3cd71a28e7d77797b4c2a0f0fb0998%22%2C%22previewModeEncryptionKey%22%3A%22aa7e494e4be8ad545d3b89401130f0cddd5cc7fad559dc5ccdc523d783aae4f3%22%7D&loadedEnvFiles=W10%3D&i18n=!

./node_modules/@node-rs/helper/lib/loader.js
Critical dependency: require function is used in a way in which dependencies cannot be statically extracted

Import trace for requested module:
./node_modules/@node-rs/helper/lib/index.js
./node_modules/@swc/core/index.js
./pages/index.js
./node_modules/next/dist/build/webpack/loaders/next-serverless-loader/index.js?page=%2F&absolutePagePath=private-next-pages%2Findex.js&absoluteAppPath=private-next-pages%2F_app.js&absoluteDocumentPath=next%2Fdist%2Fpages%2F_document&absoluteErrorPath=next%2Fdist%2Fpages%2F_error&absolute404Path=&distDir=private-dot-next&buildId=F68DPEy1I2QGOb0HZBdlW&assetPrefix=&generateEtags=true&poweredByHeader=true&canonicalBase=&basePath=&runtimeConfig=&previewProps=%7B%22previewModeId%22%3A%224c311bacc47c8a7607930533d8c1f4cc%22%2C%22previewModeSigningKey%22%3A%222e3076d32e5c50bd18f737e4f78d3fcd3a3cd71a28e7d77797b4c2a0f0fb0998%22%2C%22previewModeEncryptionKey%22%3A%22aa7e494e4be8ad545d3b89401130f0cddd5cc7fad559dc5ccdc523d783aae4f3%22%7D&loadedEnvFiles=W10%3D&i18n=!

./node_modules/@node-rs/helper/lib/loader.js
Critical dependency: the request of a dependency is an expression

Import trace for requested module:
./node_modules/@node-rs/helper/lib/index.js
./node_modules/@swc/core/index.js
./pages/index.js
./node_modules/next/dist/build/webpack/loaders/next-serverless-loader/index.js?page=%2F&absolutePagePath=private-next-pages%2Findex.js&absoluteAppPath=private-next-pages%2F_app.js&absoluteDocumentPath=next%2Fdist%2Fpages%2F_document&absoluteErrorPath=next%2Fdist%2Fpages%2F_error&absolute404Path=&distDir=private-dot-next&buildId=F68DPEy1I2QGOb0HZBdlW&assetPrefix=&generateEtags=true&poweredByHeader=true&canonicalBase=&basePath=&runtimeConfig=&previewProps=%7B%22previewModeId%22%3A%224c311bacc47c8a7607930533d8c1f4cc%22%2C%22previewModeSigningKey%22%3A%222e3076d32e5c50bd18f737e4f78d3fcd3a3cd71a28e7d77797b4c2a0f0fb0998%22%2C%22previewModeEncryptionKey%22%3A%22aa7e494e4be8ad545d3b89401130f0cddd5cc7fad559dc5ccdc523d783aae4f3%22%7D&loadedEnvFiles=W10%3D&i18n=!

./node_modules/@node-rs/helper/lib/loader.js
Critical dependency: require function is used in a way in which dependencies cannot be statically extracted

Import trace for requested module:
./node_modules/@node-rs/helper/lib/index.js
./node_modules/@swc/core/index.js
./pages/index.js
./node_modules/next/dist/build/webpack/loaders/next-serverless-loader/index.js?page=%2F&absolutePagePath=private-next-pages%2Findex.js&absoluteAppPath=private-next-pages%2F_app.js&absoluteDocumentPath=next%2Fdist%2Fpages%2F_document&absoluteErrorPath=next%2Fdist%2Fpages%2F_error&absolute404Path=&distDir=private-dot-next&buildId=F68DPEy1I2QGOb0HZBdlW&assetPrefix=&generateEtags=true&poweredByHeader=true&canonicalBase=&basePath=&runtimeConfig=&previewProps=%7B%22previewModeId%22%3A%224c311bacc47c8a7607930533d8c1f4cc%22%2C%22previewModeSigningKey%22%3A%222e3076d32e5c50bd18f737e4f78d3fcd3a3cd71a28e7d77797b4c2a0f0fb0998%22%2C%22previewModeEncryptionKey%22%3A%22aa7e494e4be8ad545d3b89401130f0cddd5cc7fad559dc5ccdc523d783aae4f3%22%7D&loadedEnvFiles=W10%3D&i18n=!

./node_modules/@swc/core/index.js
Critical dependency: the request of a dependency is an expression

Import trace for requested module:
./pages/index.js
./node_modules/next/dist/build/webpack/loaders/next-serverless-loader/index.js?page=%2F&absolutePagePath=private-next-pages%2Findex.js&absoluteAppPath=private-next-pages%2F_app.js&absoluteDocumentPath=next%2Fdist%2Fpages%2F_document&absoluteErrorPath=next%2Fdist%2Fpages%2F_error&absolute404Path=&distDir=private-dot-next&buildId=F68DPEy1I2QGOb0HZBdlW&assetPrefix=&generateEtags=true&poweredByHeader=true&canonicalBase=&basePath=&runtimeConfig=&previewProps=%7B%22previewModeId%22%3A%224c311bacc47c8a7607930533d8c1f4cc%22%2C%22previewModeSigningKey%22%3A%222e3076d32e5c50bd18f737e4f78d3fcd3a3cd71a28e7d77797b4c2a0f0fb0998%22%2C%22previewModeEncryptionKey%22%3A%22aa7e494e4be8ad545d3b89401130f0cddd5cc7fad559dc5ccdc523d783aae4f3%22%7D&loadedEnvFiles=W10%3D&i18n=!

./node_modules/@swc/core/spack.js
Critical dependency: the request of a dependency is an expression

Import trace for requested module:
./node_modules/@swc/core/index.js
./pages/index.js
./node_modules/next/dist/build/webpack/loaders/next-serverless-loader/index.js?page=%2F&absolutePagePath=private-next-pages%2Findex.js&absoluteAppPath=private-next-pages%2F_app.js&absoluteDocumentPath=next%2Fdist%2Fpages%2F_document&absoluteErrorPath=next%2Fdist%2Fpages%2F_error&absolute404Path=&distDir=private-dot-next&buildId=F68DPEy1I2QGOb0HZBdlW&assetPrefix=&generateEtags=true&poweredByHeader=true&canonicalBase=&basePath=&runtimeConfig=&previewProps=%7B%22previewModeId%22%3A%224c311bacc47c8a7607930533d8c1f4cc%22%2C%22previewModeSigningKey%22%3A%222e3076d32e5c50bd18f737e4f78d3fcd3a3cd71a28e7d77797b4c2a0f0fb0998%22%2C%22previewModeEncryptionKey%22%3A%22aa7e494e4be8ad545d3b89401130f0cddd5cc7fad559dc5ccdc523d783aae4f3%22%7D&loadedEnvFiles=W10%3D&i18n=!


> Build error occurred
Error: Can not load bindings

    at Object.loadBinding (/Users/kevin/repos/critical-dep/.next/serverless/chunks/882.js:71:11)
    at Object.7925 (/Users/kevin/repos/critical-dep/.next/serverless/chunks/882.js:129:110)
    at __webpack_require__ (/Users/kevin/repos/critical-dep/.next/serverless/webpack-runtime.js:25:43)
    at Module.3678 (/Users/kevin/repos/critical-dep/.next/serverless/pages/index.js:177:67)
    at __webpack_require__ (/Users/kevin/repos/critical-dep/.next/serverless/webpack-runtime.js:25:43)
    at Module.731 (/Users/kevin/repos/critical-dep/.next/serverless/pages/index.js:100:23)
    at __webpack_require__ (/Users/kevin/repos/critical-dep/.next/serverless/webpack-runtime.js:25:43)
    at __webpack_exec__ (/Users/kevin/repos/critical-dep/.next/serverless/pages/index.js:390:39)
    at /Users/kevin/repos/critical-dep/.next/serverless/pages/index.js:391:73
    at Function.__webpack_require__.X (/Users/kevin/repos/critical-dep/.next/serverless/webpack-runtime.js:150:21) {
  type: 'Error'
}
info  - Collecting page data .%
```
