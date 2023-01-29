# Mq [前端消息队列]

```
  基于Vue3 watch功能二次封装, 纯前端轻量化组件间消息队列, 只保证单频道推送消息
```

### 调用方式

```javascript
  import { ckPostMessage,  } from 'chunk-ui'
  const mq = new ckMq()
  mq.push('推送消息key', '消息体, 任意数据结构')
  mq.listener('接收消息Key', (getter: ()=>any) => {
    const data = getter() // 通过监听指定消息key, 获取指定key 的消息内容
    // ..
  })
```

### 属性

### 实例方法

```javascript
  push(key: string, data: any): void // 向队列中推送消息
  lintener(key: string, func: (getter: () => string)=>void) // 注册监听并获得消息数据
```

### 插槽

```
无
```

### 配置文件数据结构

```
无
```
