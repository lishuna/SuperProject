# ng1

- 初始化项目

  > 使用jdb-cli初始化ng1项目   ps: 项目名称最好和mis上模块名保持一致

  ```javascript
  jdb help         //查看jdb命令
  jdb init [name]  //生成项目模板并安装依赖
  ```

  > jdb-cli只在创建controller时按模块做了处理，其它js文件没有做处理，可能会导致命名冲突，引发报错
  >
  > 命名规则：jdbApp+项目名称+文件名（jdbAppDemoHybridxTestCtrl）驼峰规则

  ```javascript
  jdb create  //创建controller、filter、directive等js
  ```

  ​


- 启动项目

  > 加载过程  hybridx模块由commonIndex统一管理，加载各模块代码
  >
  > 在dist/route/router.js（由李权维护）  找到变量 ANGULAR_MODULES 增添新的hybridx模块名

  ```javascript
  # 本地调试，启动本地server
  gulp
  # Hybridx编译
  gulp * --hybridx
  # 产出dev包
  gulp dev
  # 产出dev环境代码，并启动本地server
  gulp local --env dev --platform=ios
  # 产出beta环境代码，并启动本地server
  gulp local --env beta --platform=ios
  # 产出test环境代码，并启动本地server
  gulp local --env test --platform=ios
  # 产出prod环境代码，并启动本地server
  gulp local --env prod --platform=ios
  # 产出beta包
  gulp build --env beta
  # 产出test包
  gulp build --env test
  # 产出线上包
  gulp build --env prod
  # hybridx调试 watch并将最新代码推到手机端（只支持android）
  gulp hybridxDebug --platform=android --env *
  ```

- 开发项目

  > 1、在app.js配置路由
  >
  > 默认路由 : /项目名称
  >
  > 端外跳转到二级页面：jdbclient://demo/hybridx?subpage=pagea   

  ```javascript
  var routesConfig = [{
      stateName: 'jdbAppDemoHybridx',
      data: {
          url: '/demoHybridx',
          templateUrl: '../demoHybridx/views/main.html',
          controller: 'jdbAppDemoHybridxCtrl'
      }
  },{
      stateName: 'jdbAppDemoHybridxPageA',
      data: {
          url: '/demoHybridx/pagea',
          templateUrl: '../demoHybridx/views/main.html',
          controller: 'jdbAppDemoHybridxCtrl'
      }
  }];
  ```

  > 2、在dist/route/route.js中搜索 `ANGULAR_MODULES`添加hybrdix模块（其他环境由李权维护）

  ![](http://officalcms.b0.upaiyun.com/2017/0906/20170906023503361.png)

  ​

  > 3、ionic1生命周期函数 

  ```javascript
  $ionicView.loaded      // 视图已经被加载
  $ionicView.beforeEnter // 视图即将被打开变成活动页面
  $ionicView.enter       // 进入视图并被激活
  $ionicView.beforeLeave // 视图将被关闭
  $ionicView.leave       // 离开视图
  ```

  ​