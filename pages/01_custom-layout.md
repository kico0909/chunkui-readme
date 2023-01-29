# custom-layout [自定义布局]

```
  基于element-plus封装的自定义布局组件
```

### 调用方式

```html
  <ck-custom-layout ...attrs... >
    <template #solt-name="{...attrs}">
      ...
    </template>
  </ck-custom-layout>
```

### 属性

|属性|类型|必填|默认值|说明|
| - | - | --- |-|-|
| mode |string|非必填|view|自定义布局的显示模式: <br>预览模式: view <br>设计模式: edit|
| conf |object|必填|无|用于编辑或用于显示布局的配置文件<br>ps.编辑模式下需要通过v-model进行双向绑定|
| editPanelWidth |number|非必填|500|编辑面板的默认宽度|

### 方法

  ```
  无
  ```

### 插槽

##### 设计[edit]模式下

|插槽名称|传入值|描述|
|-|-|-|
|colShow|data[object]: 配置的组件数据|-|
|colSetup|component[object]: 组件的配置信息 <br> setCol[function]: 用于向布局中回存组件配置信息的回调函数|-|

##### 预览[view]模式下

|插槽名称|传入值|描述|
|-|-|-|
|component|component: 组件配置信息|每一个布局位插入的组件配置信息|

### 配置文件数据结构

```json
{
  "box": [{}
  ]
}
```
