# 效果展示

- 安装借贷宝app，地址：http://client-jenkins.jdb-dev.com:8080/

- 打开app，摇一摇 >>> 环境切换 >>> 选择相应环境，这里选择test。

- 连接charlse，抓包查看请求。

  ```javascript
  在 'http://100.73.49.10'或者 'test.jiedaibao.com'下
  'mybankv21/phpsync/sync/hybrid/getRouterList'   //下发路由表
  'mybankv21/phpsync/sync/hybrid/getCodeFile'     //下发hybrid包
  ```

  > hybridx是否下发，比对md5值。
  >
  > router包是否包含新增hybridx模块

  ​

  ![](http://officalcms.b0.upaiyun.com/2017/0906/20170906015548497.png)

  ​

  ![](http://officalcms.b0.upaiyun.com/2017/0906/20170906015629905.png)

  ​

- 使用端内扫一扫功能，扫描带有跳转路由信息的二维码，打开hybridx模块

- 端内调试 

  > 1、打开hybrid模块 点击hyx浮标 在tools中有 debug脚本 可以加载本地文件 便于调试
  >
  > 2、android可以使用adb push 将hybrid包push到手机内，可以不用总是mis发布。

