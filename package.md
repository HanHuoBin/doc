# 订单相关接口

 * [套餐列表](#packagelist)
 * [下单](#orderplace)
 * [游戏地区列表（服）](#gamearealist)
 * [游戏列表](#gamelist)
 * [游戏下线路列表](#gameiplist)


<h2 id="packagelist">套餐列表</h2>

  POST /api/v1/package/list

** 请求参数 **

|参数名称|说明|类型|是否必须|
|---|---|---|---|

无

** 返回参数 **

|参数名称|说明|类型|是否必须|
|---|---|---|---|
|id|ID|int|是|
|name|套餐名称|String|是|
|money|套餐价格|float|是|

```json
{
  "bool": 1,
  "msg": "ok",
  "code": 200,
  "data": [
    {
      "id": 1,
      "name": "6元1周",
      "money": "6.00"
    },
    {
      "id": 2,
      "name": "15元1月",
      "money": "15.00"
    },
    {
      "id": 3,
      "name": "40元3月",
      "money": "40.00"
    },
    {
      "id": 4,
      "name": "120元1年",
      "money": "120.00"
    },
    {
      "id": 5,
      "name": "300元3年",
      "money": "300.00"
    },
    {
      "id": 6,
      "name": "999永久",
      "money": "999.00"
    }
  ]
}
```

<h2 id="orderplace">下单</h2>

  POST /api/v1/order/place

** 请求参数 **

|参数名称|说明|类型|是否必须|
|---|---|---|---|
|packageId|套餐ID|int|是|
|payType|支付方式：1/微信，2/支付宝|int|是|

```json
{
  "packageId": "1",
  "type": "1"
}
```

** 返回参数 **

|参数名称|说明|类型|是否必须|
|---|---|---|---|
|orderId|订单ID|int|是|


```json
{
  "bool": 1,
  "msg": "ok",
  "code": 200,
  "data": {
    "orderId": "2"
  }
}
```

<h2 id="gamearealist">游戏地区列表（服）</h2>

  POST /api/v1/gamearea/list

** 请求参数 **

|参数名称|说明|类型|是否必须|
|---|---|---|---|

无

** 返回参数 **

|参数名称|说明|类型|是否必须|
|---|---|---|---|
|id|ID|int|是|
|name|游戏名称|String|是|
|guid|GUID|String|是|

```json
{
  "bool": 1,
  "msg": "ok",
  "code": 200,
  "data": [
    {
      "id": 1,
      "name": "亚服",
      "guid": "9D908951-FA14-2AB2-76D4-5A786D76B38035"
    },
    {
      "id": 2,
      "name": "日服",
      "guid": "C77E7F5A-BBDB-368E-3445-5A786D96EE104B"
    },
    {
      "id": 3,
      "name": "欧服",
      "guid": "33C35A4A-4514-66EC-7E75-5A786D9FDC2528"
    },
    {
      "id": 4,
      "name": "台服",
      "guid": "30DB0AE2-65F5-A52C-3257-5A786DA6766DF6"
    },
    {
      "id": 5,
      "name": "美服",
      "guid": "33F4EB00-3ACF-39EB-E41F-5A786DAD43C0FF"
    }
  ]
}
```

<h2 id="gamelist">游戏列表</h2>

  POST /api/v1/game/list

** 请求参数 **

|参数名称|说明|类型|是否必须|
|---|---|---|---|
|game_area_guid|地区，区服|String|是|

```json
{
  "game_area_guid": "8359041C-34EB-34E0-E3AE-5A786DC4B0EEAC"
}
```

** 返回参数 **

|参数名称|说明|类型|是否必须|
|---|---|---|---|
|id|ID|int|是|
|name|游戏名称|String|是|
|icon|游戏图标|String|是|
|guid|GUID|String|是|

```json
{
  "bool": 1,
  "msg": "ok",
  "code": 200,
  "data": [
    {
      "id": 25,
      "name": "彩虹6号（亚服）",
      "icon": "",
      "guid": "4D36D602-6603-129A-4252-5A78718A9DA0EF"
    },
    {
      "id": 26,
      "name": "彩虹6号（亚服）",
      "icon": "",
      "guid": "C8858C57-FE5B-90E0-7530-5A78718AFDE288"
    },
    {
      "id": 27,
      "name": "彩虹6号（亚服）",
      "icon": "",
      "guid": "35B2E412-A63B-3B68-4EDB-5A78718BF6B0D3"
    },
    {
      "id": 28,
      "name": "英雄联盟",
      "icon": "",
      "guid": "F3023C7A-6474-3C27-AB35-5A78719642A695"
    },
    {
      "id": 29,
      "name": "英雄联盟",
      "icon": "",
      "guid": "C1D1E113-FB22-B501-41CA-5A79D057711BB5"
    }
  ]
}
```

<h2 id="gameiplist">游戏下线路列表</h2>

  POST /api/v1/gameip/list

** 请求参数 **

|参数名称|说明|类型|是否必须|
|---|---|---|---|
|game_guid|游戏GUID|String|是|

```json
{
  "game_guid": "DBC39A79-B95A-D4E8-44CF-5A787125984AEA"
}
```

** 返回参数 **

|参数名称|说明|类型|是否必须|
|---|---|---|---|
|id|ID|int|是|
|name|游戏名称|String|是|
|ip|IP|String|是|

```json
{
  "bool": 1,
  "msg": "ok",
  "code": 200,
  "data": [
    {
      "id": 1,
      "name": "华北1",
      "ip": "127.0.0.1"
    },
    {
      "id": 2,
      "name": "华北2",
      "ip": "127.0.0.1"
    },
    {
      "id": 3,
      "name": "华北3",
      "ip": "127.0.0.1"
    },
    {
      "id": 4,
      "name": "华北4",
      "ip": "127.0.0.1"
    },
    {
      "id": 5,
      "name": "华北5",
      "ip": "127.0.0.1"
    }
  ]
}
```



## 支付

  POST /api/v1/order/pay

** 请求参数 **

|参数名称|说明|类型|是否必须|
|---|---|---|---|
