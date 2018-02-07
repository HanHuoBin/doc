# 接口文档

## 说明

### 通讯协议

  请求采用Http协议


|请求类型|请求域名|
|---|---|
|HTTP POST/GET;application/json;charset=utf-8|http://dianlong.io/|

### 消息结构

 * http请求头，请求方式```POST``` or ```GET```方式，在每个接口都有指定声明
 * 请求报文与响应报文均用json格式
 * 请求头添加```Accept-Token```参数作为用户的登录标识

### 报文格式

例如：

** 请求报文 **
```
{
  "mobile":"18757110824",
  "password":"96e79218965eb72c92a549dd5a330112"
}
```

** 响应报文 **
```
{
  "bool": 1,
  "msg": "登录成功",
  "code": 200,
  "data": {
    "id": 3,
    "phone": "18757110824",
    "token": "3354d11737c59f25ed392f56de6bd3c0af457c06",
    "userName": "",
    "money": 0,
    "guid": "6FB28140-11B0-9C99-0451-5A6C476B610696"
  }
}
```

## [用户相关Api](member.md.html)

## [订单相关接口](package.md.html)
