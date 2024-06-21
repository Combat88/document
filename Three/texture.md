在 Three.js 中,有以下几个常用于加载纹理的工具类:
1. **THREE.TextureLoader**:
   - 功能:
     - 用于加载各种格式的 2D 纹理,如 JPG、PNG 等。
   - 示例:
     ```javascript
     const textureLoader = new THREE.TextureLoader();
     const texture = textureLoader.load('path/to/texture.jpg');
     const material = new THREE.MeshBasicMaterial({ map: texture });
     ```

2. **THREE.CubeTextureLoader**:
   - 功能:
     - 用于加载立方体纹理(cubemap),也称为天空盒纹理。
   - 示例:
     ```javascript
     const cubeTextureLoader = new THREE.CubeTextureLoader();
     cubeTextureLoader.setPath('path/to/textures/');
     const textureCube = cubeTextureLoader.load([
       'px.png', 'nx.png',
       'py.png', 'ny.png',
       'pz.png', 'nz.png'
     ]);
     const material = new THREE.MeshBasicMaterial({ envMap: textureCube });
     ```

3. **THREE.ArrayTextureLoader**:
   - 功能:
     - 用于加载多个 2D 纹理组成的数组。
   - 示例:
     ```javascript
     const arrayTextureLoader = new THREE.ArrayTextureLoader();
     arrayTextureLoader.load(
       ['path/to/texture1.jpg', 'path/to/texture2.jpg', 'path/to/texture3.jpg'],
       (textures) => {
         // 使用 textures 数组
         const material = new THREE.MeshBasicMaterial({ map: textures[0] });
       }
     );
     ```

4. **THREE.DataTextureLoader**:
   - 功能:
     - 用于加载存储于 Uint8Array、Float32Array 或 Uint16Array 的 2D 纹理数据。
   - 示例:
     ```javascript
     const dataTextureLoader = new THREE.DataTextureLoader();
     dataTextureLoader.load(
       new Uint8Array([255, 255, 255, 255]), // 纹理数据
       (texture) => {
         // 使用 texture 对象
         const material = new THREE.MeshBasicMaterial({ map: texture });
       }
     );
     ```

5. **THREE.ImageBitmapLoader**:
   - 功能:
     - 用于使用 ImageBitmap API 加载 2D 纹理,可能会比 `THREE.TextureLoader` 更高效。
   - 示例:
     ```javascript
     const imageBitmapLoader = new THREE.ImageBitmapLoader();
     imageBitmapLoader.load(
       'path/to/texture.jpg',
       (imageBitmap) => {
         const texture = new THREE.Texture(imageBitmap);
         texture.needsUpdate = true;
         const material = new THREE.MeshBasicMaterial({ map: texture });
       }
     );
     ```

这些工具类提供了不同的纹理加载方式,您可以根据需求选择合适的类来加载所需的纹理。例如,`THREE.TextureLoader` 适用于加载常规 2D 纹理,`THREE.CubeTextureLoader` 适用于加载天空盒纹理,`THREE.DataTextureLoader` 适用于加载自定义的纹理数据等。