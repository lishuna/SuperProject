# ng2

- 初始化项目

  > 使用ngu初始化ng2项目   ps: 项目名称最好和mis上模块名保持一致

  ```javascript
  //查看ngu命令
  ngu help         
  //初始化项目
  ngu g project projectName  
  //更新项目模块依赖
  ngu sync  
  //安装项目模块依赖
  npm i 
  ```

  > NGU命令

  ```javascript
  serve [options]         Serve the app with JIT mode for development.  [aliases: s]
  serve:webapp [options]  Serve the webapp with JIT mode for development.  [aliases: s]
  lint                    Lint your code.    [aliases: l]
  sync [options]          update project dependencies     [aliases: sync]

  options：
  --skipUpdate           skip auto update     
    
  //生成page
  ngu g page test
  //生成component
  ngu g component test
  //生成service
  ngu g service test

  注：生成的文件需要手动引用
  ```



* JIT && AOT

  | JIT  | app运行时  | 快    | -    | -       | app运行时   | 低    |
  | ---- | ------- | ---- | ---- | ------- | -------- | ---- |
  | 编译方式 | 编译时机    | 构建速度 | 打包大小 | 性能/渲染速度 | 模板错误检查时间 | 安全性  |
  | AOT  | app构建阶段 | 慢    | -    | 更快      | app构建阶段  | 高    |



- 启动项目

  ```javascript
  ngu serve
  ```