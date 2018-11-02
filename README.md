# parcel-polymer-repro

## Repro steps

1. `npm i`
2. `bower install` (yes, you will unfortunately need to `npm i -g bower` for this repro)
2. `npm run build`

It should crash with a `Maximum call stack size exceeded` like the following:

```
> parcel-polymer-repro@1.0.0 build C:\Users\vanca\Desktop\parcel-polymer-repro
> parcel build src/index.html --out-dir dist --public-url ./

×  C:\Users\vanca\Desktop\parcel-polymer-repro\bower_components\polymer\lib\utils\html-tag.html: Maximum call stack size exceeded
    at Array.sort (native)
    at objectHash (C:\Users\vanca\Desktop\parcel-polymer-repro\node_modules\parcel-bundler\src\utils\objectHash.js:5:39)
    at objectHash (C:\Users\vanca\Desktop\parcel-polymer-repro\node_modules\parcel-bundler\src\utils\objectHash.js:8:25)
    at objectHash (C:\Users\vanca\Desktop\parcel-polymer-repro\node_modules\parcel-bundler\src\utils\objectHash.js:8:25)
    at objectHash (C:\Users\vanca\Desktop\parcel-polymer-repro\node_modules\parcel-bundler\src\utils\objectHash.js:8:25)
    at objectHash (C:\Users\vanca\Desktop\parcel-polymer-repro\node_modules\parcel-bundler\src\utils\objectHash.js:8:25)
    at objectHash (C:\Users\vanca\Desktop\parcel-polymer-repro\node_modules\parcel-bundler\src\utils\objectHash.js:8:25)
    at objectHash (C:\Users\vanca\Desktop\parcel-polymer-repro\node_modules\parcel-bundler\src\utils\objectHash.js:8:25)
    at objectHash (C:\Users\vanca\Desktop\parcel-polymer-repro\node_modules\parcel-bundler\src\utils\objectHash.js:8:25)
    at objectHash (C:\Users\vanca\Desktop\parcel-polymer-repro\node_modules\parcel-bundler\src\utils\objectHash.js:8:25)
```


If you change `browserslist` in `package.json` to `since 2017`, the crash will not occur.
