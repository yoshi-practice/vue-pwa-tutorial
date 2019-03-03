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
