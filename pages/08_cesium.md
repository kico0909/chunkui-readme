# cesium [超图GIS中级封装组件]

```
  ...
```

### 调用方式

```html
  <ck-cesium ...attrs... >
    <temlate #soltName> ... </template>
  </ck-cesium>
```

### 属性

  |属性|类型|必填|默认值|说明|
  |-|-|-|-|-|
  | cesium | object | 必填 | - |原始超图SDK定义|
  | label-imagery | string | 非必填 | 影像图层类型 | 选择在线的影像图层服务, 可选: tianditu / bingmap / arcgis |
  | token | string | 必填 | 地图的token | 沙盒的限制条件, 默认只限制控制父级框架, 格式: "string string string", 可选值同iframe的sandbox选项 |
  | url | string | 非必填 | 地图服务的URL | 某些地图服务需要输入指定的URL提供 |


### 方法

  | 方法名 | 说明 | 参数 | 返回值 | 备注 |
  | - | - | - | - | - |
  | viewer.get | 获得GIS操作类示例 | - | 无 | callFN中需要 return 如果是异步处理则请返回promise |
  | viewer.zoomTo | 相依缩放至 | GIS内指定实体模型  | Object | 无 |
  | viewer.flyTo | 相机飞翔至 |  GIS内指定实体模型  | Object | 无 |
  | viewer.moveTo | 相依瞬移至 | 地理信息坐标  | Object | 无 |
  | model.addGLTF | 添加GLTF模型 | 实体模型实例  | 实体模型实例 | -- |
  | model.findById | 通过模型ID查找GIS内指定模型 | 实体模型ID  | 实体模型实例 | -- |
  | camera.lock | 相机锁定 | 是否锁定缩放  | -- | -- |
  | camera.unlock | 相机解锁 | 无  | -- | -- |
  | cartesian.c3FromGeocode | 地理坐标转笛卡尔3坐标系 | 地理坐标信息lng/lat/height  | 笛卡尔3坐标实例 | -- |
  | cartesian.c2FromGeocode | 地理坐标转笛卡尔2坐标系 | 地理坐标信息lng/lat/height   | 笛卡尔2坐标实例 | -- |
  | cartesian.geocodeFromC3 | 笛卡尔3坐标系转地理坐标系 | 笛卡尔3坐标系数据  | 地理信息坐标实例 | -- |

### 事件

  | 事件名 | 说明 | 回传参数 |
  | - | - | - |
  | inited | GIS初始化完成 | 无 | 
  | clickLeft | 鼠标左键点击 | 一些坐标及选中实体相关的实例  |
  | downLeft | 鼠标左键按下 | 一些坐标及选中实体相关的实例  |
  | upLeft | 鼠标左键抬起 | 一些坐标及选中实体相关的实例  |
  | mouseMove | 鼠标移动 | 一些坐标及选中实体相关的实例  |

### 插槽

  | 插槽名 | 说明 |
  | - | - |
  | default | 界面上层默认插槽 | 
  | leftToolBox | 左侧工具栏插槽 |
  | rightToolBox | 右侧工具栏插槽 |

### 配置文件数据结构

```
...无
```