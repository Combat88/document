列举 Three.js 中常用的几何体构造函数,并按照功能和示例进行展示:
1. **基本几何体**:

   - `THREE.BoxGeometry(width, height, depth, widthSegments, heightSegments, depthSegments)`:
     - width: 宽度
     - height: 高度
     - depth: 深度
     - widthSegments: 宽度分段数
     - heightSegments: 高度分段数
     - depthSegments: 深度分段数

     ```javascript
     const geometry = new THREE.BoxGeometry(1, 1, 1, 2, 2, 2);
     ```
     创建一个大小为 1x1x1、分段数为 2x2x2 的立方体。

   - `THREE.SphereGeometry(radius, widthSegments, heightSegments, phiStart, phiLength, thetaStart, thetaLength)`:
     - radius: 半径
     - widthSegments: 水平分段数
     - heightSegments: 垂直分段数
     - phiStart: 起始角度
     - phiLength: 角度范围
     - thetaStart: 起始角度
     - thetaLength: 角度范围
     ```javascript
     const geometry = new THREE.SphereGeometry(1, 32, 32);
     ```
     创建一个半径为 1、水平和垂直分段数均为 32 的球体。

   - `THREE.PlaneGeometry(width, height, widthSegments, heightSegments)`:
     - width: 宽度
     - height: 高度
     - widthSegments: 宽度分段数
     - heightSegments: 高度分段数
     ```javascript
     const geometry = new THREE.PlaneGeometry(2, 2, 1, 1);
     ```
     创建一个宽高均为 2、分段数为 1x1 的平面。

   - `THREE.CircleGeometry(radius, segments, thetaStart, thetaLength)`:
     - radius: 半径
     - segments: 分段数
     - thetaStart: 起始角度
     - thetaLength: 角度范围
     ```javascript
     const geometry = new THREE.CircleGeometry(1, 32);
     ```
     创建一个半径为 1、分段数为 32 的圆形。

2. **扫描生成几何体**:

   - `THREE.CylinderGeometry(radiusTop, radiusBottom, height, radialSegments, heightSegments, openEnded, thetaStart, thetaLength)`:
     - radiusTop: 顶部半径
     - radiusBottom: 底部半径
     - height: 高度
     - radialSegments: 径向分段数
     - heightSegments: 高度分段数
     - openEnded: 是否开启端点
     - thetaStart: 起始角度
     - thetaLength: 角度范围
    
     ```javascript
     const geometry = new THREE.CylinderGeometry(1, 1, 2, 32, 1);
     ```
     创建一个上下半径均为 1、高度为 2、径向分段数为 32、高度分段数为 1 的圆柱体。

   - `THREE.TorusGeometry(radius, tube, radialSegments, tubularSegments, arc)`:
     - radius: 圆环半径
     - tube: 管道半径
     - radialSegments: 径向分段数
     - tubularSegments: 管道分段数
     - arc: 圆弧角度
     ```javascript
     const geometry = new THREE.TorusGeometry(1, 0.4, 16, 100);
     ```
     创建一个主半径为 1、管道半径为 0.4、径向分段数为 16、管道分段数为 100 的圆环。

   - `THREE.TorusKnotGeometry(radius, tube, radialSegments, tubularSegments, p, q, heightScale)`:
     - raius: 圆环半径
     - tube: 管道半径
     - radialSegments: 径向分段数
     - tubularSegments: 管道分段数
     - p: 管道分段数
     - q: 径向分段数
     - heightScale: 高度缩放
     ```javascript
     const geometry = new THREE.TorusKnotGeometry(1, 0.4, 64, 8);
     ```
     创建一个主半径为 1、管道半径为 0.4、径向分段数为 64、管道分段数为 8 的圆环结。

3. **其他几何体**:

   - `THREE.IcosahedronGeometry(radius, detail)`:
     - radius:半径
     - detail:细节级别
     ```javascript
     const geometry = new THREE.IcosahedronGeometry(1, 0);
     ```
     创建一个半径为 1、细节级别为 0 的二十面体。

   - `THREE.DodecahedronGeometry(radius, detail)`:
     ```javascript
     const geometry = new THREE.DodecahedronGeometry(1, 0);
     ```
     创建一个半径为 1、细节级别为 0 的十二面体。

   - `THREE.OctahedronGeometry(radius, detail)`:
     ```javascript
     const geometry = new THREE.OctahedronGeometry(1, 0);
     ```
     创建一个半径为 1、细节级别为 0 的八面体。

   - `THREE.TetrahedronGeometry(radius, detail)`:
     ```javascript
     const geometry = new THREE.TetrahedronGeometry(1, 0);
     ```
     创建一个半径为 1、细节级别为 0 的四面体。

这些构造函数可以帮助您快速创建各种几何体对象。您可以根据需要调整参数来控制几何体的尺寸和细节程度,从而满足不同的场景需求。创建好几何体对象后,通常还需要创建材质对象,并将它们组合成网格对象添加到场景中进行渲染。