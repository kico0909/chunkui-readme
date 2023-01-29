# sand-box [沙盒页面引用框架]

```
  ...
```

### 调用方式

```html
  <ck-sand-box ...attrs... />
```

### 属性

  |属性|类型|必填|默认值|说明|
  |-|-|-|-|-|
  | url |number|非必填|200|显示区域的高度|
  | json |object,string|必填|无|需要现实的json结构数据|


### 方法

  | 事件名 | 说明 | 参数 | 返回值 | 备注 |
  | - | - | - | - | - |
  | on | 对沙盒发出的消息进行监听 | key: 消息名, callFN: 收到消息后的处理方法 | 无 | callFN中需要 return 如果是异步处理则请返回promise |
  | send | 向沙盒发出消息 | key: 消息名称, data: 消息数据体  | promise | 类似于AJAX可以从promise中获得请求的结果 |

### 事件
  | 事件名 | 说明 | 回传参数 |
  | - | - | - |
  | name | 当前沙盒中iframe的name值回传 | 无 |
  | loaded | 当前iframe中页面载入完毕 | 无 |
  | change | 当前iframe中页面的URL变化或者重新载入(HASH路由的变化无法触发该事件) | 无 |

### 插槽

  ```
  无
  ```

### 配置文件数据结构

```
...无
```