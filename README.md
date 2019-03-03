# vue-pwa-tutorial

---

## 環境構築、テンプレート作成

```
$ npm install -g vue-cli

$ vue init pwa vue-pwa-tutorial
# 基本的には全てEnterでOK

? Vue build standalone 
? Install vue-router? Yes
? Use ESLint to lint your code? どちらでも
? Setup unit tests with Karma + Mocha? No
? Setup e2e tests with Nightwatch? No

$ cd vue-pwa-tutorial
$ npm install
$ npm run dev
```

## ビルド
```
$ npm run build
```

## Workboxの導入
```
$ npm install workbox-webpack-plugin --save-dev
```

./build/webpack.prod.conf.js:line14
```
const SWPrecacheWebpackPlugin = require('sw-precache-webpack-plugin')
```
をコメントアウトし、
```
const WorkboxPlugin = require('workbox-webpack-plugin')
```
を追加。また、

```
new SWPrecacheWebpackPlugin({
    cacheId: 'easy-wallet',
    filename: 'service-worker.js',
    staticFileGlobs: ['dist/**/*.{js,html,css}'],
    minify: true,
    stripPrefix: 'dist/'
})
```
をコメントアウトし、
```
new WorkboxPlugin.GenerateSW({
    cacheId: 'easy-wallet',
    globDirectory: config.build.assetsRoot,
    globPatterns: ['**/*.{html,js,css,jpg,png}'],
    swDest: path.join(config.build.assetsRoot, 'service-worker.js'),
    skipWaiting: true,
    clientsClaim: true,
    runtimeCaching: []
})
```
を追加。