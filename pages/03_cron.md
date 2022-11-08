# cron

```
  基于crontab的周期调度配置信息合成工具
```

### 调用方式

```html
  <ck-cron ...attrs... />
```

### 属性
|属性|类型|必填|默认值|说明|
|-|-|-|-|-|
| cronValue |string|非必填|无|用于初始化的值|
| i18n |string|非必填|cn|可选项cn/en|
| maxHeight |string|非必填|400px|-|
| showBtn |boolean|非必填|false|是否显示组件自带的功能按钮|

### 方法
  |方法名|描述|
  |-|-|
  |Submit|用户获得配置完成的周期调度字符串|
  |Reset|用于清空配置的周期调度字符串|
