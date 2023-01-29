# Mq [前端消息队列]

```
  基于Vue3 watch功能二次封装, 纯前端轻量化组件间消息队列, 只保证单频道推送消息
```

### 调用方式

```typescript
  import { ckPostMessage } from 'chunk-ui'
  const ckPM = new ckPostMessage(Window)
  ckPM.send('发送的消息Key', '发送的消息数据').then(rs => {
    // 发送消息后得到的返回值
  })
  ckPM.on('要处理的消息key', (data: any) => {
    // 接收到消息后的处理内动
  })
```

### 属性

### 实例方法

```typescript
  send(key: string, data: any): void // 向iframe中推送消息
  on(key: string, func: (d: any) => promise) // 处理指定消息的方法监听
```

### 插槽

```
无
```

### 配置文件数据结构

```
无
```
