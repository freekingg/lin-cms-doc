---
title: 全局配置
---

Lin 框架内置的全局配置项都在`config/index.js`文件里。

## 用户无操作自动登出

1. 是否开启无操作跳出

```js
openAutoJumpOut: true, // 默认开启
```

2. 若开启，配置多长时间无操作将跳出

```js
stagnateTime: 1 * 60 * 60 * 1000, // 默认1小时
```

出于安全考虑，在 1 个小时的时间内，如果系统化无任何用户操作( `页面路由跳转` 和 `向后台发起请求` )，会自动退出账号并跳转到登录页面，确保管理员长期不在的时候其他人无法使用该系统。

:::tip
大多数用户为了方便会默认记住登录账号和登录密码，这样也意味着即使账号登出了，任何人都可以重新登录系统，所以安全性和便捷性需要使用者自己衡量。
:::

## API 请求地址

```js
baseUrl: process.env.VUE_APP_BASE_URL 
```

本地开发阶段配置本地虚拟域名(`http://localhost:5000/`)，线上部署生产域名。

## 无需登录即可访问的路由

```js
 notLoginRoute: ['login'],
```

## 默认采用后端返回异常

```js
useFrontEndErrorMsg: false,
```

针对同一个错误码，前端展示给用户的提示可以在前端定义，在 `error-code.js` 中定义，默认直接展示后端返回的异常信息。