## SceneKit
使用高级别的场景描述方式创建3D游戏和向APP中添加3D内容。轻松添加动画、物理模拟、粒子效果和基于真实感的物理渲染。
### Overview
SceneKit结合了高性能的渲染引擎与用于导入，操作，和渲染3D资源的描述性API。与Metal和OpenGL等这样的要求您精确地实现显示场景的渲染算法细节的低级API不同，SceneKit只需要描述场景的内容以及您希望它执行的动作或动画。

## Topics
### First Steps
* [class SCNScene](https://github.com/Mr-Wei/SceneKitDocumentation/blob/master/SceneKit/SCNScene/SCNScene.md) 

	节点层级视图和全局属性的容器，共同形成可显示的3D场景。
* class SCNView

	显示3D场景内容的视图。

### Scene Structure 场景结构

* 使用节点来安排一个场景

	使用节点来定义一个场景的结构。

* class SCNNode
	
	场景图的结构元素，表示三维坐标空间中的位置和变换，您可以将几何图形、灯光、照相机或其他可显示内容附加到该坐标空间中。

* class SCNReferenceNode

	场景图节点，用于从单独的场景文件加载内容的占位符。
	
### Display and Interactivity 显示与交互
* protocol SCNSceneRenderer
	
	SCNView,SCNLayer,SCNRenderer共有的方法和属性

* protocol SCNSceneRendererDelegate

	提供了一些方法，App可以通过实现他们参与SceneKit的动画循环或执行额外的渲染。

* class SCNLayer
	
	一个CoreAnimation layer，通过它可以根据一个SceneKit场景的内容来做出渲染。

* class SCNRenderer

	在现有的Metal工作流或OpenGL上下文中显示SceneKit场景的渲染器。

* class SCNHitTestResult
	
	包含了场景控件和视图空间对场景元素的搜索结果的相关信息。
	
### Lighting, Cameras, and Shading 光线,摄像机和阴影
* class SCNLight
	
	一种可以被添加到节点上来点亮场景的光源。

* class SCNCamera
	
	一组摄像机属性，可以被添加到节点上，以提供一个用来显示场景的视点。

* class SCNMaterial

	一组阴影属性，用于定义渲染时几何体表面的外观。
* class SCNMaterialProperty
	
	一个用来存放材料的某种视觉特性的颜色或纹理的容器。

### Geometry 几何体
* class SCNGeometry

	一种三维形状（也称为模型或网格），可以在场景中显示，附带材料可以定义其外观。

* class SCNGeometrySource
	
	顶点数据的容器，是组成三维物体或几何体定义的一部分。

* class SCNGeometryElement

	索引数据的容器，描述了顶点是如何连接的，同样用来定义三维体或几何体。

* 内置的几何体类型
	
	从2D文本和贝塞尔曲线生成的3D对象的基本形状（例如球体, 盒子,飞机等）和特征。
	
### Animation and Constraints 动画和约束
* 动画
	
	通过按照预先设定好的方式移动场景中的元素来创建声明式动画，或者管理通过外部工具导入的动画。

* 约束
	
	根据特定的规则，自动调节节点的位置和方向。

* class SCNSkinner
	
	管理骨骼动画和动画中的节点与几何体之间关系的对象。

* class SCNMorpher
	
	管理节点基础几何体和一个或多个目标几何体之间平滑过渡的对象。
	
### Physics 物理现象
* 物理模拟
	向场景元素添加动态行为，检测接触和碰撞，模拟重力、弹簧和车辆等逼真效果。
	
### Particle Systems 粒子系统
* class SCNParticleSystem
	
	使用高级仿真对你指定的一般动作对小图像精灵系统做动画和模拟的对象。
* class SCNParticlePropertyController
	
	由粒子系统渲染的独立的粒子的单个属性的动画
	
* 根据Document Browser View Controller创建App
	
	实现一个自定义文档文件格式来管理用户与不同的云存储提供者存储的文件之间的互动。
	
### Audio 音频

* class SCNAudioSource
	
	一个简单的, 可复用的音频源（从文件中加载的音乐或者音效），用于位置性音频的播放。

* class SCNAudioPlayer
	
	在SceneKit场景中播放位置性音源的控制器。
	
### Renderer Customization 渲染器的自定义
* protocol SCNShadable

	使用Metal或OpenGL着色器程序渲染自定义SceneKit几何体和材质的方法

* class SCNProgram
	
	一个完整的Metal或OpenGL着色器程序，它取代了SceneKit对几何体或材质的渲染。

* protocol SCNBufferStream

	使用自定义着色器管理Metal缓冲区的对象

* class SCNTechnique
	
	使用自定义的Metal或者OpenGL着色器的额外的绘图通道来增强或者后期处理SceneKit的渲染场景的规则。
	
* protocol SCNTechniqueSupport
	
	SceneKit对象的通用接口，支持使用SCNTechnique对象进行多路渲染。
	
* protocol SCNNodeRendererDelegate
	
	可以自行实现的一些方法，通过这些方法可以使用自定义Metal或OpenGL绘图代码来渲染节点的内容。
	
### Scene Asset Import 场景资源导入
* class SCNSceneSource 
	
	管理与从文件或数据加载场景内容相关联的数据读取任务的对象。

### JavaScript
* func SCNExportJavaScriptModule(JSContext)

	使SceneKit类和全局常量可用于指定的JavaScript上下文。

### SceneKit Data Types
*	SceneKit 3D Data Types
	
	SceneKit特定的向量，矩阵以及相关的函数和操作。
