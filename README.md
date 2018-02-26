# TNWZ
头脑王者开房答题抓题库 & 排位自动答题脚本

*免责声明：仅供研究使用，请勿进行非法用途。*

### [掘金文章: 我是如何次次《头脑王者》获得满分的](https://juejin.im/post/5a5b4097518825734d149423)

[![](https://badge.juejin.im/entry/5a5b59126fb9a01cae0f9a4e/likes.svg?style=flat)](https://juejin.im/post/5a5b4097518825734d149423)

### 环境要求
1. node v7.6以上
2. mongodb
3. anyproxy

#### 安装anyproxy
```
1. 安装node.js
2. npm i -g anyproxy
3. anyproxy-ca // 生成证书
4. anyproxy -i // 以代理https的方式启动
// 然后手机端配置代理的IP及PORT，默认端口为8001，
// Anyproxy的WebService的默认端口为8002，这里可以查看到接口
// 手机端配置代理以后需要下载证书并信任，
// 苹果端的可以在手机的Safiri里面输入xxx.xxx.xxx.xxx:8002/fetchCrtFile的方式下载到证书
// 高版本的iOS可能需要在两处地方信任。
```
#### 先做以下操作
1. git clone（或者直接DownLoad即可）
2. npm install 或 yarn install （这个是安装依赖包的，装了node以后就会有npm命令了）
3. 开启mongodb数据库 （数据开启了不要关闭，或者是以服务的形式启动）

### 模拟开房对战
*（不包含题库，需要先通过这个获取题库，预测题库总数在17200左右，目前我已经采集17148题，准确率在99%+）*
1. 填写index.js文件中2个对战用户的 uid & token
2. npm run start 执行脚本

*注意： 偶尔会出现未结算重新登录的提示，这时可能需要把两个账号重新登录或者点一下排位再退出）*

### 模拟排位（等题库规模达到1.5W以后，就会正确率极高）
1. 填写modify-response.js中的token（目前token不填也没关系）
2. 手机信任证书并连上代理
3. npm run fight 执行脚本

* 注意： 执行脚本以后，手机需要连上代理，然后点击进入排位页面，这时候命令行会提示开始战斗，说明是成功执行了，然后选择推荐答案即可（！！表示），也可以自动打开代码中的自动提交的注释，0延时提交，不过可能有封号风险 *

### 特别说明一下常见问题
1. 目前IOS10测试的时候发现，经常会提示断开连接，但是只需要在排位页面先断开wifi然后连上再点击排位即可（已修复）

2. IOS11将无法使用该脚本，原因是Anyproxy对websocket包的解析有些问题，这个有没有大佬尝试一下的（已修复）

3. 题库需要自行爬取，是为了增加一下难度希望大家慎用该脚本

<img src="https://s1.ax1x.com/2018/01/17/pD1p36.jpg" width="200" height="200" />
<img src="https://s1.ax1x.com/2018/01/17/pDDhEq.jpg" width="200" height="200" />
