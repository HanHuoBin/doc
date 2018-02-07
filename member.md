# 用户相关

 * [注册](#register)
 * [登录](#login)
 * [忘记密码](#forget)
 * [发送验证码](#sendsms)

<h2 id="register">注册</h2>

  POST /api/v1/public/register

** 请求参数 **

|参数名称|说明|类型|是否必须|
|---|---|---|---|
|mobile|手机号|String|是|
|code|验证码|String|是|
|password|密码|String|是|

```json
{
  "mobile": "18757110824",
  "code": "348980",
  "password": "123456"
}
```

** 返回参数 **

|参数名称|说明|类型|是否必须|
|---|---|---|---|
|memberId|用户ID|int|是|

```json
{
  "bool": 1,
  "msg": "ok",
  "code": 200,
  "data": {
    "memberId": "3"
  }
}
```



<h2 id="login">登录</h2>

  POST /api/v1/public/register

** 请求参数 **

|参数名称|说明|类型|是否必须|
|---|---|---|---|
|mobile|用户名|String|是|
|password|密码|String|是|


```json
{
  "username": "18757110824",
  "password": "e10adc3949ba59abbe56e057f20f883e"
}
```

** 返回参数 **

|参数名称|说明|类型|是否必须|
|---|---|---|---|
|id|用户ID|int|是|
|guid|GUID|String|是|
|phone|手机号|String|是|
|money|账户余额|float|是|
|token|Token|String|是|
|userName|用户名|String|否|

```json
{
  "bool": 1,
  "msg": "登录成功",
  "code": 200,
  "data": {
    "id": 3,
    "phone": "18757110824",
    "token": "5a8ea86d61f36178f3cde1ff4c40e49b88e9608d",
    "userName": "",
    "money": 0,
    "guid": "6FB28140-11B0-9C99-0451-5A6C476B610696"
  }
}
```

<h2 id="forget">忘记密码</h2>

  POST /api/v1/public/forget

** 请求参数 **

|参数名称|说明|类型|是否必须|
|---|---|---|---|
|mobile|手机号|String|是|
|code|验证码|String|是|
|password|密码|String|是|

```json
{
  "mobile": "18757110824",
  "password": "96e79218965eb72c92a549dd5a330112",
  "code": "447135"
}
```

** 返回参数 **

|参数名称|说明|类型|是否必须|
|---|---|---|---|
|status|1表示成功|int|是|

```json
{
  "bool": 1,
  "msg": "修改密码成功",
  "code": 200,
  "data": {
    "status": 1
  }
}
```

<h2 id="sendsms">发送验证码</h2>

  POST /api/v1/public/sendsms

** 请求参数 **

|参数名称|说明|类型|是否必须|
|---|---|---|---|
|mobile|手机号|String|是|
|type|类型|int|是|

说明：
  * type 1：注册，2：忘记密码

```json
{
  "mobile": "18757110824",
  "type": "2"
}
```


** 返回参数 **

|参数名称|说明|类型|是否必须|
|---|---|---|---|
|code|验证码|String|是|

```json
{
  "bool": 1,
  "msg": "发送成功",
  "code": 200,
  "data": {
    "code": 102823
  }
}
```
