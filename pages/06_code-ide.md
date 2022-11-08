# charts [代码编辑器]

```
  基于ECharts的可视化图组件,
```

### 调用方式

```html
  <ck-charts ...attrs... />
```

### 属性

|属性|类型|必填|默认值|说明|
|-|-|-|-|-|
| title |string|非必填|无|图的标题|
| hook |object|非必填|无|钩子<br>before[function]: 图初始化前钩子 <br>inited[function]: 图完成初始化后的钩子|
| data |object|必填|无|显示图所要显示的数据,数据结构同e-charts的option属性中series的数据结构|
| option |object|非必填|无|显示图所要显示的数据,数据结构同e-charts的option属性数据结构,该属性中传入series属性无效|

### 方法

  ```
  无
  ```

### 插槽

```
无
```

<!-- |插槽名称|传入值|描述|
|-|-|-|
|colShow|data[object]: 配置的组件数据|-|
|colSetup|component[object]: 组件的配置信息 <br> setCol[function]: 用于向布局中回存组件配置信息的回调函数|-| -->


### 配置文件数据结构

###### option的数据结构

```json
请参见echarts的option.属性数据结构
```

###### data的数据结构

```json
请参见echarts的option.series属性数据结构
```
