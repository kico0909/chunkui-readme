# chunk-ui组件功能说明书

```
  基于element-plus等基础组件二次封装的高级业务组件,主要用于基于vue3框架的快速业务开发
  内置集成element-plus版本: V2.2.17
```
* 内置集成的第三方包
  * codemirror: 6.0.0,
  * echarts: 5.4.0,
  * element-plus: 2.2.17,
  * js-beautify: 1.14.6,
  * sql-formatter: 7.0.3,
  * vue-codemirror: 6.0.0,
  * @codemirror/lang-java: 6.0.0,
  * @codemirror/lang-javascript: 6.0.2,
  * @codemirror/lang-sql: 6.0.0,
  * @codemirror/theme-one-dark: 6.0.0,
  * "vue3-uuid": "1.0.0"


* 业务UI组件
  * [custom-layout](/pages/01_custom-layout.md): 自定义布局
  * [custom-table](/pages/02_custom-table.md): 自定义表单
  * [cron](/pages/03_cron.md): 周期调度定义
  * [charts](/pages/04_charts.md): Echarts的高级封装
  * [show-json](/pages/05_show-json.md): json格式化显示工具
  * [code-ide](/pages/06_code-ide.md): 基于CodeMirror的代码编辑工具

* 功能性
  * [ajax](/pages/sys01_ajax.md): 基于fetch的轻量化ajax组件
  * [MQ](/pages/sys02_mq.md): 基于Vue3轻量化的组件间消息队列