# custom-table [自定义表单]

```
  基于element-plus封装的自定义表单组件
```

### 调用方式

```html
<ck-custom-table
  :data="tableData.data"
  :tableInfo="tableData.tableInfo"
  :templateData="tableData.template"
  :authData="tableData.authData"
  :initScript="tableData.initScript"
  :beforeSubmitScript="tableData.beforeSubmitScript"
  :afterSubmitScript="tableData.afterSubmitScript"
  :scripts="tableData.scripts"
  :selectOptions="tableData.selectOptions"
  @optionKeys="handleGetOptions"
  @selector-click="handleSelectorClick"
></ck-custom-table>
```

### 属性

| 属性 | 类型| 必填 | 默认值 | 说明 |
| - | - | - | - | - |
| data | TableDataType（见下方) | 非必填 | 无 | 表单整体展示数据（前台预览必传，编辑非必传，后台非必传），此数据会在后台配置后保存回调会返回此数据（默认数据为空的结构形数据）。|
| mode | string | 非必填 | "view" | 可选值："edit"，"view"，"config" <br> 'view' 或 'edit' 或 ''（代表开启前台表单模式，默认是前台表单，这里的表单模式代表表单的编辑权限，编辑及查看权限受控于 authData 数据）。后台配置模块传 'config'。 |
| tableInfo | TableInfoType （见下方） | 非必填 | 无     | 表单的基础信息，非必传，后台会在配置后生成给调用的开发者，但前台要求必传 。 |
| templateData | ElementType[] （见下方） | 非必填 | 无     | 表单的模板数据，后台非必传，前台必传 。 |
| authData           | AuthDataType （见下方）       | 非必填 | 无     | 表单组件的权限数据，后台配置后的保存回调会返回此数据，此时的数据为默认的全体编辑权限，前台非必传，如果不传入，表单组件的权限仅会依照后台配置时的默认属性来进行权限控制。 |
| initScript | string | 非必填 | 无     | 表单初始化后所需要运行的脚本。（如果表单内没有下拉选项，脚本会在表单初始化后立即运行一次，如有下拉组件存在，脚本会在开发者传入值集的数据后进行运行。）                                                |
| beforeSubmitScript | string | 非必填 | 无     | 表单提交前所需要运行的脚本。（需开发者调用方法进行运行） |
| afterSubmitScript  | string | 非必填 | 无     | 表单提交后所需要运行的脚本。（需开发者调用方法进行运行） |
| scripts | ElementsScriptType （见下方） | 非必填 | 无     | 组件的脚本数据，组件在改变后会调用自己的脚本数据。非必要不建议使用此功能。 |
| selectOptions | OptionsDataType （见下方）    | 非必填 | 无     | 表单选择类型组件的值集数据，表单加载完成后会回调 @optionKeys="..." 此方法，并传回所有西安则类型组件的 keys:string[] ，供开发者依照此 keys 去后台请求相对应的值集数据返回。 |

### 事件

| 事件名         | 说明                                                                                | 回调参数                                                                                                                                                                                                                                                                                                                                                                              |
| -------------- | ----------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| optionKeys     | 当表单加载完成后，会返回所有选择类型组件的 selKey 集合，用于请求这些 key 的下拉数据 | ids: Array<string>                                                                                                                                                                                                                                                                                                                                                                    |
| selector-click | 点击选择器组件的回调方法                                                            | res: { selectorKey: string; elementKey: string; data: { v: Array<any>; l: Array<any>; o: Array<any>; }; mappingData: [keyName: string]: { v: Array<any>; l: Array<any>; o: Array<any> } ; <br> 参数说明：<br>selectorKey（配置表单时设置的选择器的 key），<br>elementKey（当前选择器组件的 key），<br>data（当前选择器的数据），<br>mappingData（配置表单时选择的映射字段的组件数据） |

### 方法

| 方法名 | 说明 | 回调参数 |
| - | - | - |
| getConfigData      | 【后台】获取配置表单数据的方法。  | - |
| getFormData        | 【前台】获取表单填写数据的方法。 | isCheck：boolean （默认：false），是否要求表单进行数据验证，验证是根据表单传入的权限数据来进行验证的。 |
| checkFormData      | 【前台】验证表单填写数据的正确性方法。 | 返回：boolean 值，true：验证通过，false：验证不通过。 |
| beforeSubmitScript | 【前台】运行提交前的脚本方法。 | - |
| afterSubmitScript  | 【前台】运行提交后的脚本方法。 | - |

### 插槽

`无`

### 涉及到的数据类型

```json
/**
 * @description 表单信息数据结构
 **/
interface TableInfoType {
  id?: string; // 表单id
  key?: string; // 表单key
  name: string; // 表单名称
  describe: string; // 描述信息
  creater?: string;
  createdDate?: string;
  [keyName: string]: any;
}

--------------------------------------------------------------------------------------

/**
 * @description 单个组件数据结构
 **/
interface ElementType {
  id: string; // 组件ID，元素在表单中的唯一标识 uuid
  key: string; // 不可改变的组件key
  oneToMany: boolean; // 是否是一对多，仅在 type === table 时候有用，默认 false
  type: string; // 组件类型
  options: any[]; // 预留字段（将会保存用户手动添加的options）
  optionsKey: { value: string; label: string; code: string }; // 值集的 value(key)、label(显示的名字), code()
  elements: ElementType[];
  hasChildren?: boolean; // 是否包含子组件（只有子表的时候为true）
  tableMode: string; // 子表的展示形式
  tags: any[]; // 预留
  sourceType: string; // 组件来源类型，子表组件不为空，说明是来自一对多还是一对一子的子表单。主表'main'，一对多子表'more'，一对一子表'single'
  parentKey: string; // 组件的父级key（仅子表组件不为空）
  attributes: ElementAttributesType; // 组件的基础属性
}

/**
 @description 单个组件属性数据结构
 */
interface ElementAttributesType {
  fieldId: string; // 字段id （预留字段）
  label: string; // 标题
  placeholder: string; // 占位提示
  layout: number; // 栅格 默认：12
  labelWidth: number; // 标签宽度 px 默认：140
  contentWidth: number; // 控件宽度 百分比 % 默认：100
  defaultValue: DataObjType; // 默认值
  labelShow: true; // 是否显示标签 默认：true 显示
  fieldName: string; // 字段名称 默认值 取自数据表的中文字段名称
  defaultAuthority: string; // 默认权限 默认值 'w'
  clearable: boolean; // 是否可以清楚文本内动 默认是：false
  prefix: {
    enable: boolean; // 前缀是否启用
    text: string; // 前缀描述性的文字
  };
  suffix: {
    enable: boolean; // 后缀是否启用
    text: string; // 后缀描述性的文字
  };
  maxlength: number; // input等输入类型组件的最大输入字数限制，初始值 120，最大8000，最小 1
  showWordLimit: boolean; //  是否显示技术统计 默认值 false
  rows: number; // 多行文本输入框的 行数 默认值 3，最大15，最小1
  precision: number; // 小数精确位数 默认值 2
  proportion: number; // 转换比例 默认值 1
  isMoneyMethod: boolean; // 是否开启金钱计数法 默认值 true
  multiple: boolean; // 是否开启多选 默认值 false
  multipleLimit: number; // 多选时，最大可选数量 默认值 0，最大100，最小0
  showAllLevels: boolean; // 输入框中是否显示选中值的完整路径 默认 true
  separator: string; // 选项分隔符， 默认 '/'
  expandTrigger: string; // 级联次级菜单的展开方式， 默认 'click'
  editable: boolean; // 日期选择器，文本框是否可输入 默认 false
  startPlaceholder: string; // 范围选择时开始日期的占位内容 默认 '开始日期'
  endPlaceholder: string; // 范围选择时结束日期的占位内容 默认 '结束日期'
  disableYesterday: boolean; // 是否禁用今天之前的日期 默认 false
  showTime: boolean; // 是否显示 时分秒 默认 false
  rangeSeparator: string; // 时间 选择范围时的分隔符 默认 '至'
  buttonText: string; // button 按钮文字  默认"选择" 备用字段
  regs: any[]; // 正则校验 { message: '', rule: '' }
  fileSize: number; // 上传文件大小限制
  maxUploadNum: number; // 最大上传数量 默认 3
  accept: string[]; // 上传文件的格式限定 默认 [] (全部)
  fixed: string; // 表单模式下的组件 浮动模式 默认''
  uploadPath: string; // 上传文件的配置路径 默认 ''
  popConfig: {
    selector?: {
      key: string;  // 选择器的key
      name: string; // 选择器的名称
    };
    mappingKey?: string[]; // 映射字段的 keys
    [keyName: string]: any;
  };

  [keyName: string]: any;
}

--------------------------------------------------------------------------------------

/**
 * @description 单个组件的保存数据的数据类型
 **/
interface DataObjType {
  v: Array<any>;
  l: Array<any>;
  o: Array<any>;
}

/**
 * @description 整体自定义表单的保存数据的数据类型
 **/
interface TableDataType {
  [keyName: string]: DataObjType | any[];
}

--------------------------------------------------------------------------------------

/**
 * @description 枚举对象类型
 * @date        2022/2/11 - 3:36 PM
 **/
interface OptionsObjType {
  value: string;
  label: string;
  code: string;
  children: OptionsObjType[];
}

/**
 * @description 枚举类型组件的可供选择数据的数据类型
 **/
interface OptionsDataType {
  [keyName: string]: OptionsObjType[];
}

--------------------------------------------------------------------------------------

/**
 * @description 表单全部组件的权限数据的数据类型
 **/
interface AuthDataType {
  [keyName: string]: string;
}

--------------------------------------------------------------------------------------

/**
 * @description 表单每个组件需要的脚本数据，可仅传入某些组件的脚本数据
 **/
interface ElementsScriptType {
  [keyName: string]: string;
}

--------------------------------------------------------------------------------------



```
