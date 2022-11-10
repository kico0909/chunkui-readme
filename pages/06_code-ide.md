# charts [代码编辑器]

```
  基于CodeMirror的WebCodeIed，用于前端开发的各种业务。
```

### 调用方式

```html
<ck-code-ide
  v-model="value"
  height="200"
  :disabled="false"
  language="javascript"
>
</ck-code-ide>
```

### 属性

| 属性                 | 类型    | 必填   | 默认值     | 说明                                                                                                                   |
| -------------------- | ------- | ------ | ---------- | ---------------------------------------------------------------------------------------------------------------------- |
| modelValue / v-model | string  | 必填   | 空字符串   | 绑定值                                                                                                                 |
| height               | string  | 非必填 | 300        | 编辑器的高度                                                                                                           |
| disabled             | boolean | 非必填 | false      | 是否禁用                                                                                                               |
| language             | string  | 非必填 | javascript | 编辑器主要的语言提示，可选类型“javascript”，“json”，“css”，“html”，“java”，“sql”（目前开启选择模式，所以不必要请不传） |

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

```
无
```
