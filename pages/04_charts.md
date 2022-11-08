# charts [可视化图组件]

```
  基于ECharts的可视化图组件
  内置Echarts版本: V5.4.0
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

### 配置文件数据结构

###### option的数据结构

```json
请参见echarts的option.属性数据结构
```

###### data的数据结构

```json
请参见echarts的option.series属性数据结构
```
