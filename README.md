# single-spa-demo-01

[微前端框架 之 single-spa 从入门到精通](https://juejin.cn/post/6862661545592111111)

[liyongning/micro-frontend](https://github.com/liyongning/micro-frontend)

[./note.md](./note.md)

## 目录结构

```
app1/ ------ 子应用 1 （vue）
app2/ ------ 子应用 2 （vue）
app3/ ------ 子应用 3 （react）
layout/ ---- 主应用 （vue）
```

## 包管理器

Yarn

## 各应用启动命令

### 各子应用独立运行

app1、app2 相同

```bash
yarn serve
```

app3

```bash
yarn start
```

### 作为子应用运行

layout

```bash
yarn serve
```

app1、app2 相同

```bash
yarn serve:micro
```

app3

```bash
yarn start
```

## 打包

在各个项目的根目录下分别执行

```bash
yarn build
```

## 部署

> 如果部署到 nginx 上，需要注意 nginx 的代理配置
>
> - 对于子应用静态资源的加载只需要拦截相应的前缀将请求转发到对应子应用的目录下即可
> - 页面刷新只需要拦截到主应用即可，主应用内部自己根据 activeWhen 去挂载对应的子应用
