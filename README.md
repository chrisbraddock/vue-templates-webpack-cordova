# vue-templates-webpack-cordova

> minimal application of Cordova to [vue-webpack-boilerplate](https://github.com/vuejs-templates/webpack)

An attempt to add the "minimum" amount of code necessary the Vue Webpack
template while adding [Cordova](https://cordova.apache.org/) support.

The first few commits should be a good diff to look at if you're after the same.
I made sure to commit virgin template files, prior to adding the Cordova code
in one commit.

The code uses [vue-cordova](https://github.com/kartsims/vue-cordova) and looted
its [vue-cordova-demo repo](https://github.com/kartsims/vue-cordova-demo) for
most bits of working code.


**notes:**

I symlinked `www` to `dist` to make Cordova happy. I liked this better than the
other methods I've seen because I was able to make fewer changes to the Webpack
template. Other methods typically changed `index` and `assetsRoots`
in config/index.js.


Use the latest dev version of the Cordova iOS platform to avoid the
[issue I hit](http://stackoverflow.com/a/39591319/227260) when I tried to
deploy to an actual device from the command line.

```
cordova platform remove ios && cordova platform add https://github.com/apache/cordova-ios.git
```  
  
This issue also requires you to set your `developmentTeam` in build.json (for
non-emulator deployment anyway).

I did have to change `assetsPublicPath` in config/index.js to get things working
in Cordova. Unfortunately, I don't know all the implications of that change.
I'll be using the code so I'll come back and correct if needed. :)

## Build Setup

``` bash
# install dependencies
npm install

# add a mobile platform or two
cordova platform add https://github.com/apache/cordova-ios.git
cordova platform add android

# run Vue/Cordova
cordova emulate ios
cordova run ios --device
# or `npm run ios` / `npm run ios:device`

# of course you can still:

# serve with hot reload at localhost:8080
npm run dev

# build for production with minification
npm run build

# build for production with minification
npm run build
```
