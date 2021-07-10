# 笔记

- 改造子应用时，通常是在**子应用的入口文件**暴露加载、卸载等生命周期函数给主应用
- vue 子应用独立运行和作为子应用运行时， base url 是不同的。如何做到？
  - 通过启动的脚本命令进行传参 `—mode micro`，匹配到环境文件 .env.micro，在该文件中配置 `VUE_APP_BASE_URL=/app1`，然后路由文件中通过 `base: process.env.VUE_APP_BASE_URL` 获取 base url。
  - 总结：脚本命令传参 → 匹配环境文件 → 获取环境文件中的环境变量，进行设置
  - package.json 脚本命令、.env、.env.xxxMode、progress.env.yyy（如：progress.env.NODE_ENV、progress.env.VUE_APP_BASE_URL）的配合使用
