# ajax [异步请求类]

```
  基于fetch进行二次封装的,轻量化异步请求类
```

### 调用方式

```typescript
  import { ckAjax, TAjaxReturn } from 'chunk-ui'
  const ajax = new ckAjax()
  ajax.post('url', '发送的数据'): Promise<TAjaxReturn<T>>
```

### 属性

### 实例方法

```typescript
  setHeader({[key: string]: any}): void // 设置请求头
  post(url, params?, header?): Promise<TAjaxReturn<T>> // 发起post请求
  get(url, params?, header?): Promise<TAjaxReturn<T>> // 发起get请求
  put(url, params?, header?): Promise<TAjaxReturn<T>> // 发起put请求
  delete(url, params?, header?): Promise<TAjaxReturn<T>> // 发起delete请求
```

### 插槽

```
无
```

### 配置文件数据结构

```
无
```
