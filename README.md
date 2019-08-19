# angular 8 oauth2 oidc base

## 依赖

- [angular 8](https://www.angular.cn/)
- [angular-oauth2-oidc](https://manfredsteyer.github.io/angular-oauth2-oidc/docs/)

## 特点

- 支持单点登录
- 默认走 sessionStorage 存储，关闭浏览器自动清除登录状态
- 支持外部配置 auth 设置 `[计划中]`

## 修改配置

下面列举最常用的三个配置
打开 `app.component.ts` 中的 configure 方法中：

- `issuer` 配置认证服务器
- `redirectUri` 配置回调页
- `clientId` 配置 client 唯一 id。

## 基本操作

### 登录

```js
this.oauthService.initLoginFlow();
```

### 登录回调

```js
const claims = this.oauthService.getIdentityClaims();
```

打印 claims 看看具体的数据结构吧。

### 登出

```js
this.oauthService.logOut();
```

## 附

由于 `app` 组件（壳组件）是必须执行的，所以说目前来说即便没有 guard 也会自动跳转登录。

另外本项目使用的 sessionStorage 存储，因此可以关闭浏览器以清除登录状态。
