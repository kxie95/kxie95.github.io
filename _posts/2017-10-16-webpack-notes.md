---
layout:     post
title:      "Webpack notes"
date:       2017-10-16 16:40:00
summary:    "" 
categories: webpack
---

* With vue, you need a vue-loader to translate .vue files.
* If you want to use vue with typescript, you need the ts-loader. awesome-typescript-loader doesn't play nice with vue right now.
* You need to add appendtssuffixto in ts-loader so that it can preprocess the .vue files. Adds .ts to .vue files as name suggests.
* Use dev-server to server app with webpack config.
* Need some crazy css loaders within vue-loader to read the css.
* resolve.alias allows you to import vue as vue/dist/vue.esm.js
* resolve.extensions means you can import those things without those extensions.
* use html webpack plugin to generate index.html to inject your final bundle.
