# 开发项目

- HybridOpenuUrl('jdbclient://demo/hybridx') 

  ```javascript
  1、解析地址跳转，通过路由表找到对应模块地址；demo/hybridx === hybridx://www/demoHybridx
  2、实例化webview  打开  /commonindex/index.html?modeule=demoHybridx#/demo/hybridx
  3、加载本地ng1 ng2 基础代码
  4、通过modulename当前代码是ng1还是ng2项目，来展示对应的容器(content)
  5、进入到业务模块首页
  ```

  ​

- 历史堆栈

  ```javascript
  1、页面跳转保存url 如A是根路由跳转到B 再跳转到C  记录为[A,B,C]
  2、若从C跳到D [a,b,c,d]   若从C跳到b,则记录为[a,b],并清除c缓存
  3、如果当前页面是根页面，点击返回则跳回native
  ```

  ​

- 特殊业务场景

  ```javascript
  //由端或者其他webview回退到本页面触发
  jdbPageManager.bindOnResumeHandler(getData); 
  eg:$scope.butClick = function(status) {
    jdbPageManager.bindOnResumeHandler(
        $scope.update
    );
    console.log('btnClick:', status);
  };
  //跳转到的页面别为rootview
  jdbPageManager.goRoot('jdbAppPayPartnerCreditFactoryMain'); 

  //绑定左上角back点击事件，只生效一次
  jdbPageManager.bindOnceNavBackHandler(function() {
      jdbPageManager.goRoot('jdbAppPayPartnerCreditFactoryMain');
      jdbPageManager.goBack(-2);
  });
  ```

- 白屏时间优化

  ```javascript
  1、端内app做了webview优化
  2、本地缓存 localStorage  直接读取本地缓存 节省网络请求时间
  3、针对dom结构复杂项目或者无网络情况且第一次进入采取墓碑图（实验项目 贷款超市）
  ```

  ​


- 托管到gitlab

  > 在gitlab创建新项目，获取项目地址

  ```javascript
  git init
  git add .
  git cm "init"
  git remote add origin 项目地址
  git push -u origin master
  ```

