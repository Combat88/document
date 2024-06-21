列举 Three.js 中常用的材质构造函数,并按照功能和示例进行展示:

1. **材质参数**
    - parameters:
       - color: 材质的颜色,默认为白色。
       - transparent: 是否透明,默认为 false。
       - opacity: 透明度,默认为 1.0。
       - side: 渲染面,默认为正面。
       - wireframe: 是否以线框模式渲染,默认为 false。
       - wireframeLinewidth: 线框线的宽度,默认为 1.0。
       - wireframeLinecap: 线框线的线帽,默认为 'round'。
       - wireframeLinejoin: 线框线的线段连接方式,默认为 'round'。
       - vertexColors: 顶点颜色,默认为 'NoColors'。
       - fog: 是否受雾效影响,默认为 true。
       - lights: 是否受光照影响,默认为 true。
       - blending: 混合模式,默认为 'NormalBlending'。
       - depthTest: 是否开启深度测试,默认为 true。
       - depthWrite: 是否写入深度缓冲,默认为 true。
       - alphaTest: 透明度测试阈值,默认为 0.0。
       - overdraw: 过度绘制阈值,默认为 0.5。
       - shadowSide: 阴影面,默认为 'FrontSide'。
       - shadowMap: 阴影贴图,默认为 null。
       - shadowMapEnabled: 是否启用阴影贴图,默认为 false。
       - shadowMapType: 阴影贴图类型,默认为 'Basic'。
       - shadowMapDebug: 是否显示阴影贴图调试信息,默认为 false。
       - shadowMapCullFace: 阴影贴图裁剪面,默认为 'Front'。
       - shadowMapPCF: 阴影贴图PCF滤波,默认为 false。
       - shadowMapPCFOffset: 阴影贴图PCF偏移,默认为 0.0。
       - shadowMapPCFSize: 阴影贴图PCF大小,默认为 1.0。
       - shadowMapSoft: 阴影贴图软化,默认为 false。
       - shadowMapSoftSize: 阴影贴图软化大小,默认为 5.0。
       - morphTargets: 是否启用 morphTargets,默认为 false。
       - morphNormals: 是否启用 morphNormals,默认为 false。
       - skinning: 是否启用 skinning,默认为 false。
       - vertexTangents: 是否启用 vertexTangents,默认为 false。
       - map: 纹理贴图,默认为 null。
       - lightMap: 光照贴图,默认为 null。
       - lightMapIntensity: 光照贴图强度,默认为 1.0。
       - aoMap: 环境贴图,默认为 null。
       - aoMapIntensity: 环境贴图强度,默认为 1.0。
       - emissive: 自发光颜色,默认为黑色。
       - emissiveMap: 自发光贴图,默认为 null。
       - emissiveIntensity: 自发光强度,默认为 1.0。
       - specularMap: 镜面贴图,默认为 null。
       - envMap: 环境贴图,默认为 null。
       - envMapIntensity: 环境贴图强度,默认为 1.0。
       - refractionRatio: 折射率,默认为 0.98。
       - refractionMap: 折射贴图,默认为 null。
       - combine: 混合模式,默认为 'Multiply'。
       - reflectivity: 反射率,默认为 1.0。
       - refractionRatio: 折射率,默认为 0.98。
       - refractionMap: 折射贴图,默认为 null。
       - clearcoat: 光泽度,默认为 1.0。
       - clearcoatRoughness: 光泽度粗糙度,默认为 0.0。
       - clearcoatNormalMap: 光泽度法线贴图,默认为 null。
       - clearcoatNormalScale: 光泽度法线贴图缩放,默认为 new THREE.Vector2(1.0, 1.0)。
       - clearcoatMap: 光泽度贴图,默认为 null。
       - clearcoatRoughnessMap: 光泽度粗糙度贴图,默认为 null。
       

2. **基础材质**:

   - `THREE.MeshBasicMaterial(parameters)`:
     ```javascript
     const material = new THREE.MeshBasicMaterial({ color: 0xff0000 });
     ```
     创建一个红色的基础材质,不受光照影响。

   - `THREE.MeshLambertMaterial(parameters)`:
     ```javascript
     const material = new THREE.MeshLambertMaterial({ color: 0x00ff00 });
     ```
     创建一个绿色的兰伯特材质,受光照影响。

   - `THREE.MeshPhongMaterial(parameters)`:
     ```javascript
     const material = new THREE.MeshPhongMaterial({ color: 0x0000ff, specular: 0xffffff, shininess: 50 });
     ```
     创建一个蓝色的高光材质,具有高光效果。

3. **物理材质**:

   - `THREE.MeshStandardMaterial(parameters)`:
     ```javascript
     const material = new THREE.MeshStandardMaterial({ color: 0xffffff, roughness: 0.5, metalness: 0.5 });
     ```
     创建一个白色的实时物理材质,通过 `roughness` 和 `metalness` 参数控制材质的属性。

   - `THREE.MeshPhysicalMaterial(parameters)`:
     ```javascript
     const material = new THREE.MeshPhysicalMaterial({ color: 0xffffff, roughness: 0.2, metalness: 0.8, clearcoat: 1.0, clearcoatRoughness: 0.2 });
     ```
     创建一个高级物理材质,可以模拟不同材质,如金属、塑料、玻璃等。

4. **纹理材质**:

   - `THREE.MeshStandardMaterial(parameters)`:
     ```javascript
     const texture = new THREE.TextureLoader().load('path/to/texture.jpg');
     const material = new THREE.MeshStandardMaterial({ map: texture });
     ```
     创建一个使用纹理贴图的标准材质。

   - `THREE.MeshBasicMaterial(parameters)`:
     ```javascript
     const texture = new THREE.TextureLoader().load('path/to/texture.png');
     const material = new THREE.MeshBasicMaterial({ map: texture });
     ```
     创建一个使用纹理贴图的基础材质。

5. **特殊材质**:

   - `THREE.MeshDepthMaterial(parameters)`:
     ```javascript
     const material = new THREE.MeshDepthMaterial();
     ```
     创建一个深度材质,用于可视化深度信息。

   - `THREE.MeshNormalMaterial(parameters)`:
     ```javascript
     const material = new THREE.MeshNormalMaterial();
     ```
     创建一个法线材质,用于可视化法线信息。

   - `THREE.LineBasicMaterial(parameters)`:
     ```javascript
     const material = new THREE.LineBasicMaterial({ color: 0x00ff00 });
     ```
     创建一个用于渲染线条的基础线材质。

这些材质构造函数可以帮助您快速创建各种材质对象,从基础的颜色材质到高级的物理材质,再到特殊用途的材质。您可以根据需要调整参数来控制材质的外观和属性,以满足不同的渲染需求。创建好材质对象后,通常还需要创建几何体对象,并将它们组合成网格对象添加到场景中进行渲染。