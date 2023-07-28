# glTF Draco Compressor

## 🖊️ ~ Overview

This repository compresses glTF files exported from cg software (Blender, etc.) into glb files.
install packages

## 🎮 ~ Getting Started

node: v.17.0.0
npm: 8.1.0

※ Operation confirmed version

```
// install
npm i

// compressor
npm run draco
```

## 🤓 ~ How to use

Place the gltf file in /src/.

run npm run meshopt

If you have a zipped glb file inside the /dist/ you are done

## 🌏 ~ Three.js

Confirmed to work with three.js r148

- [three/examples/jsm/libs/draco](https://github.com/mrdoob/three.js/tree/master/examples/jsm/libs/draco)

```js
import * as THREE from "three";
import { GLTFLoader } from "three/examples/jsm/loaders/GLTFLoader.js";
import { DRACOLoader } from "three/examples/jsm/loaders/DRACOLoader";

const dracoLoader = new DRACOLoader();
dracoLoader.setDecoderPath("three/examples/jsm/libs/draco/");

const loader = new GLTFLoader();
loader.setDRACOLoader(dracoLoader);

async function init() {
  const glb = loader.loadAsync("./[filename]-draco.glb");
  const model = glb.scene;
  scene.add(model);
}
```

## 🏠 ~ Repository structure

```
/
├── dist/
│   └── [filename]-draco.glb // compressed glb file
├── libs/ // It is a library stored in three.js
│   └── draco/*
├── node_modules/
├── src/
│   └── [filename].gltf // before compression
├── .gitignore
├── compress-draco.js
├── package-lock.json
├── package.json
└── Readme.md
```

## 📝 ~ Note

### [glTF Viewer](https://gltf-viewer.donmccurdy.com/)

This is a site where you can check if the glb and gltf files are displayed correctly on the web.

### Package

- [gltfpack](https://www.npmjs.com/package/gltfpack)

### Reference Site

- [Node.js で glTF モデルを圧縮して three.js で読み込む（DRACO/meshoptimizer）](https://qiita.com/watabo_shi/items/ba6c76f4158f827f69ed)
