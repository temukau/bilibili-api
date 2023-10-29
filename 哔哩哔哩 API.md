---
title: 哔哩哔哩 API v1.0.0
language_tabs:
  - shell: Shell
  - http: HTTP
  - javascript: JavaScript
  - ruby: Ruby
  - python: Python
  - php: PHP
  - java: Java
  - go: Go
toc_footers: []
includes: []
search: true
code_clipboard: true
highlight_theme: darkula
headingLevel: 2
generator: "@tarslib/widdershins v4.0.17"

---

# 哔哩哔哩 API

> v1.0.0

基于哔哩哔哩官方网站、小程序、APP分析

Base URLs:

* <a href="https://api.bilibili.com/">正式环境: https://api.bilibili.com/</a>

# Authentication

# 动态

## GET 动态页关注列表

GET /x/polymer/web-dynamic/v1/portal

[https://t.bilibili.com/](https://t.bilibili.com/)

### 请求参数

|名称|位置|类型|必选|说明|
|---|---|---|---|---|
|User-Agent|header|string| 否 |none|

> 返回示例

> 成功

```json
{
  "code": -101,
  "message": "账号未登录",
  "ttl": 1
}
```

### 返回结果

|状态码|状态码含义|说明|数据模型|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|成功|Inline|

### 返回数据结构

## GET 动态列表 (需要登录)

GET /x/polymer/web-dynamic/v1/feed/all

### 请求参数

|名称|位置|类型|必选|说明|
|---|---|---|---|---|
|type|query|string| 是 |类型: all全部, video视频投稿, pgc追番追剧, article专栏|
|platform|query|string| 是 |平台|
|page|query|string| 是 |页码|
|host_mid|query|string| 是 |用户id，不传则为关注的全部动态|
|User-Agent|header|string| 否 |none|

> 返回示例

> 200 Response

```json
{}
```

### 返回结果

|状态码|状态码含义|说明|数据模型|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|成功|Inline|

### 返回数据结构

## GET 热门动态 (无需登录)

GET /x/polymer/web-dynamic/v1/feed/hot

### 请求参数

|名称|位置|类型|必选|说明|
|---|---|---|---|---|
|page|query|string| 否 |none|
|User-Agent|header|string| 否 |none|

> 返回示例

> 200 Response

```json
{
  "code": 0,
  "message": "string",
  "ttl": 0,
  "data": {
    "has_more": true,
    "items": [
      {
        "basic": {
          "comment_id_str": "string",
          "comment_type": 0,
          "like_icon": {},
          "rid_str": "string"
        },
        "id_str": "string",
        "modules": {
          "module_author": {},
          "module_dynamic": {},
          "module_interaction": {},
          "module_more": {},
          "module_stat": {},
          "module_tag": {}
        },
        "type": "string",
        "visible": true
      }
    ],
    "offset": null,
    "update_baseline": "string",
    "update_num": null
  }
}
```

### 返回结果

|状态码|状态码含义|说明|数据模型|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|成功|Inline|

### 返回数据结构

状态码 **200**

|名称|类型|必选|约束|中文名|说明|
|---|---|---|---|---|---|
|» code|integer|true|none||none|
|» message|string|true|none||none|
|» ttl|integer|true|none||none|
|» data|object|true|none||none|
|»» has_more|boolean|true|none||none|
|»» items|[object]|true|none||none|
|»»» basic|object|true|none||none|
|»»»» comment_id_str|string|true|none||none|
|»»»» comment_type|integer|true|none||none|
|»»»» like_icon|object|true|none||none|
|»»»»» action_url|string|true|none||none|
|»»»»» end_url|string|true|none||none|
|»»»»» id|integer|true|none||none|
|»»»»» start_url|string|true|none||none|
|»»»» rid_str|string|true|none||none|
|»»» id_str|string|true|none||none|
|»»» modules|object|true|none||none|
|»»»» module_author|object|true|none||none|
|»»»»» avatar|object|true|none||none|
|»»»»»» container_size|object|true|none||none|
|»»»»»»» height|number|true|none||none|
|»»»»»»» width|number|true|none||none|
|»»»»»» fallback_layers|object|true|none||none|
|»»»»»»» is_critical_group|boolean|true|none||none|
|»»»»»»» layers|[object]|true|none||none|
|»»»»»»»» general_spec|object|true|none||none|
|»»»»»»»»» pos_spec|object|true|none||none|
|»»»»»»»»»» axis_x|number|true|none||none|
|»»»»»»»»»» axis_y|number|true|none||none|
|»»»»»»»»»» coordinate_pos|integer|true|none||none|
|»»»»»»»»» render_spec|object|true|none||none|
|»»»»»»»»»» opacity|integer|true|none||none|
|»»»»»»»»» size_spec|object|true|none||none|
|»»»»»»»»»» height|integer|true|none||none|
|»»»»»»»»»» width|integer|true|none||none|
|»»»»»»»» layer_config|object|true|none||none|
|»»»»»»»»» is_critical|boolean|false|none||none|
|»»»»»»»»» tags|object|true|none||none|
|»»»»»»»»»» AVATAR_LAYER|object|false|none||none|
|»»»»»»»»»» GENERAL_CFG|object|true|none||none|
|»»»»»»»»»»» config_type|integer|true|none||none|
|»»»»»»»»»»» general_config|object|true|none||none|
|»»»»»»»»»»»» web_css_style|object|true|none||none|
|»»»»»»»»»»»»» borderRadius|string|true|none||none|
|»»»»»»»»»»»»» background-color|string|true|none||none|
|»»»»»»»»»»»»» border|string|true|none||none|
|»»»»»»»»»»»»» boxSizing|string|true|none||none|
|»»»»»»»»»» ICON_LAYER|object|true|none||none|
|»»»»»»»» resource|object|true|none||none|
|»»»»»»»»» res_image|object|true|none||none|
|»»»»»»»»»» image_src|object|true|none||none|
|»»»»»»»»»»» placeholder|integer|false|none||none|
|»»»»»»»»»»» remote|object|false|none||none|
|»»»»»»»»»»»» bfs_style|string|true|none||none|
|»»»»»»»»»»»» url|string|true|none||none|
|»»»»»»»»»»» src_type|integer|true|none||none|
|»»»»»»»»»»» local|integer|true|none||none|
|»»»»»»»»» res_type|integer|true|none||none|
|»»»»»»»» visible|boolean|true|none||none|
|»»»»»» mid|string|true|none||none|
|»»»»» face|string|true|none||none|
|»»»»» face_nft|boolean|true|none||none|
|»»»»» following|null|true|none||none|
|»»»»» jump_url|string|true|none||none|
|»»»»» label|string|true|none||none|
|»»»»» mid|integer|true|none||none|
|»»»»» name|string|true|none||none|
|»»»»» official_verify|object|true|none||none|
|»»»»»» desc|string|true|none||none|
|»»»»»» type|integer|true|none||none|
|»»»»» pendant|object|true|none||none|
|»»»»»» expire|integer|true|none||none|
|»»»»»» image|string|true|none||none|
|»»»»»» image_enhance|string|true|none||none|
|»»»»»» image_enhance_frame|string|true|none||none|
|»»»»»» n_pid|integer|true|none||none|
|»»»»»» name|string|true|none||none|
|»»»»»» pid|integer|true|none||none|
|»»»»» pub_action|string|true|none||none|
|»»»»» pub_location_text|string|true|none||none|
|»»»»» pub_time|string|true|none||none|
|»»»»» pub_ts|integer|true|none||none|
|»»»»» type|string|true|none||none|
|»»»»» vip|object|true|none||none|
|»»»»»» avatar_subscript|integer|true|none||none|
|»»»»»» avatar_subscript_url|string|true|none||none|
|»»»»»» due_date|integer|true|none||none|
|»»»»»» label|object|true|none||none|
|»»»»»»» bg_color|string|true|none||none|
|»»»»»»» bg_style|integer|true|none||none|
|»»»»»»» border_color|string|true|none||none|
|»»»»»»» img_label_uri_hans|string|true|none||none|
|»»»»»»» img_label_uri_hans_static|string|true|none||none|
|»»»»»»» img_label_uri_hant|string|true|none||none|
|»»»»»»» img_label_uri_hant_static|string|true|none||none|
|»»»»»»» label_theme|string|true|none||none|
|»»»»»»» path|string|true|none||none|
|»»»»»»» text|string|true|none||none|
|»»»»»»» text_color|string|true|none||none|
|»»»»»»» use_img_label|boolean|true|none||none|
|»»»»»» nickname_color|string|true|none||none|
|»»»»»» status|integer|true|none||none|
|»»»»»» theme_type|integer|true|none||none|
|»»»»»» type|integer|true|none||none|
|»»»»» decorate|object|true|none||none|
|»»»»»» card_url|string|true|none||none|
|»»»»»» fan|object|true|none||none|
|»»»»»»» color|string|true|none||none|
|»»»»»»» is_fan|boolean|true|none||none|
|»»»»»»» num_str|string|true|none||none|
|»»»»»»» number|integer|true|none||none|
|»»»»»» id|integer|true|none||none|
|»»»»»» jump_url|string|true|none||none|
|»»»»»» name|string|true|none||none|
|»»»»»» type|integer|true|none||none|
|»»»» module_dynamic|object|true|none||none|
|»»»»» additional|object¦null|true|none||none|
|»»»»»» common|object|true|none||none|
|»»»»»»» button|object|true|none||none|
|»»»»»»»» check|object|true|none||none|
|»»»»»»»»» icon_url|string|true|none||none|
|»»»»»»»»» text|string|true|none||none|
|»»»»»»»» status|integer|true|none||none|
|»»»»»»»» type|integer|true|none||none|
|»»»»»»»» uncheck|object|true|none||none|
|»»»»»»»»» icon_url|string|true|none||none|
|»»»»»»»»» text|string|true|none||none|
|»»»»»»» cover|string|true|none||none|
|»»»»»»» desc1|string|true|none||none|
|»»»»»»» desc2|string|true|none||none|
|»»»»»»» head_text|string|true|none||none|
|»»»»»»» id_str|string|true|none||none|
|»»»»»»» jump_url|string|true|none||none|
|»»»»»»» style|integer|true|none||none|
|»»»»»»» sub_type|string|true|none||none|
|»»»»»»» title|string|true|none||none|
|»»»»»» type|string|true|none||none|
|»»»»» desc|object|true|none||none|
|»»»»»» rich_text_nodes|[object]|true|none||none|
|»»»»»»» orig_text|string|true|none||none|
|»»»»»»» text|string|true|none||none|
|»»»»»»» type|string|true|none||none|
|»»»»»»» jump_url|string|true|none||none|
|»»»»»»» rid|string|false|none||none|
|»»»»»» text|string|true|none||none|
|»»»»» major|object|true|none||none|
|»»»»»» draw|object|true|none||none|
|»»»»»»» id|integer|true|none||none|
|»»»»»»» items|[object]|true|none||none|
|»»»»»»»» height|integer|true|none||none|
|»»»»»»»» size|number|true|none||none|
|»»»»»»»» src|string|true|none||none|
|»»»»»»»» tags|[string]|true|none||none|
|»»»»»»»» width|integer|true|none||none|
|»»»»»» type|string|true|none||none|
|»»»»» topic|null|true|none||none|
|»»»» module_interaction|object|false|none||none|
|»»»»» items|[object]|true|none||none|
|»»»»»» desc|object|false|none||none|
|»»»»»»» rich_text_nodes|[object]|true|none||none|
|»»»»»»»» orig_text|string|true|none||none|
|»»»»»»»» rid|string|false|none||none|
|»»»»»»»» text|string|true|none||none|
|»»»»»»»» type|string|true|none||none|
|»»»»»»» text|string|true|none||none|
|»»»»»» type|integer|false|none||none|
|»»»» module_more|object|true|none||none|
|»»»»» three_point_items|[object]|true|none||none|
|»»»»»» label|string|true|none||none|
|»»»»»» type|string|true|none||none|
|»»»» module_stat|object|true|none||none|
|»»»»» comment|object|true|none||none|
|»»»»»» count|integer|true|none||none|
|»»»»»» forbidden|boolean|true|none||none|
|»»»»» forward|object|true|none||none|
|»»»»»» count|integer|true|none||none|
|»»»»»» forbidden|boolean|true|none||none|
|»»»»» like|object|true|none||none|
|»»»»»» count|integer|true|none||none|
|»»»»»» forbidden|boolean|true|none||none|
|»»»»»» status|boolean|true|none||none|
|»»»» module_tag|object|false|none||none|
|»»»»» text|string|true|none||none|
|»»» type|string|true|none||none|
|»»» visible|boolean|true|none||none|
|»» offset|null|true|none||none|
|»» update_baseline|string|true|none||none|
|»» update_num|null|true|none||none|

# 用户

## GET 我的信息

GET /x/space/v2/myinfo

### 请求参数

|名称|位置|类型|必选|说明|
|---|---|---|---|---|
|User-Agent|header|string| 否 |none|

> 返回示例

> 失败

```json
{
  "code": -101,
  "message": "账号未登录",
  "ttl": 1
}
```

### 返回结果

|状态码|状态码含义|说明|数据模型|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|失败|Inline|

### 返回数据结构

状态码 **200**

|名称|类型|必选|约束|中文名|说明|
|---|---|---|---|---|---|
|» code|integer|true|none||错误码|
|» message|string|true|none||错误信息|
|» ttl|integer|true|none||none|

## GET 关注列表

GET /x/relation/followings

### 请求参数

|名称|位置|类型|必选|说明|
|---|---|---|---|---|
|vmid|query|string| 是 |用户id|
|pn|query|string| 是 |页码|
|ps|query|string| 是 |每页数量|
|order|query|string| 是 |排序方式|
|order_type|query|string| 是 |排序类型|
|User-Agent|header|string| 否 |none|

> 返回示例

> 失败示例 - 未登录

```json
{
  "code": -101,
  "message": "账号未登录",
  "ttl": 1
}
```

### 返回结果

|状态码|状态码含义|说明|数据模型|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|失败示例 - 未登录|Inline|

### 返回数据结构

状态码 **200**

|名称|类型|必选|约束|中文名|说明|
|---|---|---|---|---|---|
|» code|integer|true|none||none|
|» message|string|true|none||none|
|» ttl|integer|true|none||none|

## GET 经验记录

GET /x/member/web/exp/log

### 请求参数

|名称|位置|类型|必选|说明|
|---|---|---|---|---|
|SESSDATA|cookie|string| 否 |none|
|csrf|query|string| 否 |none|
|jsonp|query|string| 否 |none|
|User-Agent|header|string| 否 |none|

> 返回示例

> 200 Response

```json
{
  "code": 0,
  "message": "string",
  "ttl": 0,
  "data": {
    "list": [
      {
        "delta": 0,
        "time": "string",
        "reason": "string"
      }
    ],
    "count": 0
  }
}
```

### 返回结果

|状态码|状态码含义|说明|数据模型|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|成功|Inline|

### 返回数据结构

状态码 **200**

|名称|类型|必选|约束|中文名|说明|
|---|---|---|---|---|---|
|» code|integer|true|none||none|
|» message|string|true|none||none|
|» ttl|integer|true|none||none|
|» data|object|true|none||none|
|»» list|[object]|true|none||none|
|»»» delta|integer|true|none||none|
|»»» time|string|true|none||none|
|»»» reason|string|true|none||none|
|»» count|integer|true|none||none|

## GET 稍后再看 (列表)

GET /x/v2/history/toview/web

### 请求参数

|名称|位置|类型|必选|说明|
|---|---|---|---|---|
|SESSDATA|cookie|string| 否 |none|
|User-Agent|header|string| 否 |none|

> 返回示例

> 200 Response

```json
{
  "code": 0,
  "message": "string",
  "ttl": 0,
  "data": {
    "count": 0,
    "list": [
      {
        "aid": 0,
        "videos": 0,
        "tid": 0,
        "tname": "string",
        "copyright": 0,
        "pic": "string",
        "title": "string",
        "pubdate": 0,
        "ctime": 0,
        "desc": "string",
        "state": 0,
        "duration": 0,
        "mission_id": 0,
        "rights": {
          "bp": 0,
          "elec": 0,
          "download": 0,
          "movie": 0,
          "pay": 0,
          "hd5": 0,
          "no_reprint": 0,
          "autoplay": 0,
          "ugc_pay": 0,
          "is_cooperation": 0,
          "ugc_pay_preview": 0,
          "no_background": 0,
          "arc_pay": 0,
          "pay_free_watch": 0
        },
        "owner": {
          "mid": 0,
          "name": "string",
          "face": "string"
        },
        "stat": {
          "aid": 0,
          "view": 0,
          "danmaku": 0,
          "reply": 0,
          "favorite": 0,
          "coin": 0,
          "share": 0,
          "now_rank": 0,
          "his_rank": 0,
          "like": 0,
          "dislike": 0,
          "vt": 0,
          "vv": 0
        },
        "dynamic": "string",
        "dimension": {
          "width": 0,
          "height": 0,
          "rotate": 0
        },
        "season_id": 0,
        "short_link_v2": "string",
        "up_from_v2": 0,
        "pages": [
          {
            "cid": null,
            "page": null,
            "from": null,
            "part": null,
            "duration": null,
            "vid": null,
            "weblink": null,
            "dimension": null
          }
        ],
        "cid": 0,
        "progress": 0,
        "add_at": 0,
        "bvid": "string",
        "uri": "string",
        "viewed": true,
        "seq": 0,
        "enable_vt": 0,
        "view_text_1": "string"
      }
    ]
  }
}
```

### 返回结果

|状态码|状态码含义|说明|数据模型|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|成功|Inline|

### 返回数据结构

状态码 **200**

|名称|类型|必选|约束|中文名|说明|
|---|---|---|---|---|---|
|» code|integer|true|none||none|
|» message|string|true|none||none|
|» ttl|integer|true|none||none|
|» data|object|true|none||none|
|»» count|integer|true|none||none|
|»» list|[object]|true|none||none|
|»»» aid|integer|false|none||none|
|»»» videos|integer|false|none||none|
|»»» tid|integer|false|none||none|
|»»» tname|string|false|none||none|
|»»» copyright|integer|false|none||none|
|»»» pic|string|false|none||none|
|»»» title|string|false|none||none|
|»»» pubdate|integer|false|none||none|
|»»» ctime|integer|false|none||none|
|»»» desc|string|false|none||none|
|»»» state|integer|false|none||none|
|»»» duration|integer|false|none||none|
|»»» mission_id|integer|false|none||none|
|»»» rights|object|false|none||none|
|»»»» bp|integer|true|none||none|
|»»»» elec|integer|true|none||none|
|»»»» download|integer|true|none||none|
|»»»» movie|integer|true|none||none|
|»»»» pay|integer|true|none||none|
|»»»» hd5|integer|true|none||none|
|»»»» no_reprint|integer|true|none||none|
|»»»» autoplay|integer|true|none||none|
|»»»» ugc_pay|integer|true|none||none|
|»»»» is_cooperation|integer|true|none||none|
|»»»» ugc_pay_preview|integer|true|none||none|
|»»»» no_background|integer|true|none||none|
|»»»» arc_pay|integer|true|none||none|
|»»»» pay_free_watch|integer|true|none||none|
|»»» owner|object|false|none||none|
|»»»» mid|integer|true|none||none|
|»»»» name|string|true|none||none|
|»»»» face|string|true|none||none|
|»»» stat|object|false|none||none|
|»»»» aid|integer|true|none||none|
|»»»» view|integer|true|none||none|
|»»»» danmaku|integer|true|none||none|
|»»»» reply|integer|true|none||none|
|»»»» favorite|integer|true|none||none|
|»»»» coin|integer|true|none||none|
|»»»» share|integer|true|none||none|
|»»»» now_rank|integer|true|none||none|
|»»»» his_rank|integer|true|none||none|
|»»»» like|integer|true|none||none|
|»»»» dislike|integer|true|none||none|
|»»»» vt|integer|true|none||none|
|»»»» vv|integer|true|none||none|
|»»» dynamic|string|false|none||none|
|»»» dimension|object|false|none||none|
|»»»» width|integer|true|none||none|
|»»»» height|integer|true|none||none|
|»»»» rotate|integer|true|none||none|
|»»» season_id|integer|false|none||none|
|»»» short_link_v2|string|false|none||none|
|»»» up_from_v2|integer|false|none||none|
|»»» pages|[object]|false|none||none|
|»»»» cid|integer|false|none||none|
|»»»» page|integer|false|none||none|
|»»»» from|string|false|none||none|
|»»»» part|string|false|none||none|
|»»»» duration|integer|false|none||none|
|»»»» vid|string|false|none||none|
|»»»» weblink|string|false|none||none|
|»»»» dimension|object|false|none||none|
|»»»»» width|integer|true|none||none|
|»»»»» height|integer|true|none||none|
|»»»»» rotate|integer|true|none||none|
|»»» cid|integer|false|none||none|
|»»» progress|integer|false|none||none|
|»»» add_at|integer|false|none||none|
|»»» bvid|string|false|none||none|
|»»» uri|string|false|none||none|
|»»» viewed|boolean|false|none||none|
|»»» seq|integer|false|none||none|
|»»» enable_vt|integer|false|none||none|
|»»» view_text_1|string|false|none||none|

## GET 粉丝列表

GET /x/relation/fans

### 请求参数

|名称|位置|类型|必选|说明|
|---|---|---|---|---|
|vmid|query|string| 是 |用户id|
|pn|query|string| 是 |页码|
|ps|query|string| 是 |每页数量|
|order|query|string| 是 |排序方式asc顺序，desc逆序|
|order_type|query|string| 是 |排序类型|
|User-Agent|header|string| 否 |none|

> 返回示例

> 成功

```json
{
  "code": -101,
  "message": "账号未登录",
  "ttl": 1
}
```

### 返回结果

|状态码|状态码含义|说明|数据模型|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|成功|Inline|

### 返回数据结构

## GET 用户信息

GET /x/space/wbi/acc/info

### 请求参数

|名称|位置|类型|必选|说明|
|---|---|---|---|---|
|mid|query|string| 是 |用户id|
|platform|query|string| 是 |平台|
|User-Agent|header|string| 是 |none|

> 返回示例

> 成功

```json
{
  "code": 0,
  "message": "0",
  "ttl": 1,
  "data": {
    "mid": 9094311,
    "name": "临时工小陈",
    "sex": "女",
    "face": "https://i0.hdslb.com/bfs/face/d60718e33c0e0eb42d07d88ba8eb09b9f3fcabdf.jpg",
    "face_nft": 0,
    "face_nft_type": 0,
    "sign": "我司不定期招聘老板，待遇从优\n商务请联系：Fadachai-here\n大柴工作室出品",
    "rank": 10000,
    "level": 6,
    "jointime": 0,
    "moral": 0,
    "silence": 0,
    "coins": 0,
    "fans_badge": true,
    "fans_medal": {
      "show": false,
      "wear": false,
      "medal": null
    },
    "official": {
      "role": 1,
      "title": "bilibili 知名UP主",
      "desc": "",
      "type": 0
    },
    "vip": {
      "type": 2,
      "status": 1,
      "due_date": 1698163200000,
      "vip_pay_type": 1,
      "theme_type": 0,
      "label": {
        "path": "",
        "text": "年度大会员",
        "label_theme": "annual_vip",
        "text_color": "#FFFFFF",
        "bg_style": 1,
        "bg_color": "#FB7299",
        "border_color": "",
        "use_img_label": true,
        "img_label_uri_hans": "",
        "img_label_uri_hant": "",
        "img_label_uri_hans_static": "https://i0.hdslb.com/bfs/vip/8d4f8bfc713826a5412a0a27eaaac4d6b9ede1d9.png",
        "img_label_uri_hant_static": "https://i0.hdslb.com/bfs/activity-plat/static/20220614/e369244d0b14644f5e1a06431e22a4d5/VEW8fCC0hg.png"
      },
      "avatar_subscript": 1,
      "nickname_color": "#FB7299",
      "role": 3,
      "avatar_subscript_url": "",
      "tv_vip_status": 0,
      "tv_vip_pay_type": 0,
      "tv_due_date": 0
    },
    "pendant": {
      "pid": 0,
      "name": "",
      "image": "",
      "expire": 0,
      "image_enhance": "",
      "image_enhance_frame": ""
    },
    "nameplate": {
      "nid": 0,
      "name": "",
      "image": "",
      "image_small": "",
      "level": "",
      "condition": ""
    },
    "user_honour_info": {
      "mid": 0,
      "colour": null,
      "tags": []
    },
    "is_followed": false,
    "top_photo": "http://i1.hdslb.com/bfs/space/cb1c3ef50e22b6096fde67febe863494caefebad.png",
    "theme": {},
    "sys_notice": {},
    "live_room": {
      "roomStatus": 1,
      "liveStatus": 0,
      "url": "https://live.bilibili.com/526557?broadcast_type=0&is_room_feed=1",
      "title": "临时工小陈",
      "cover": "http://i0.hdslb.com/bfs/live/user_cover/68bb969ac002ba8ceb452a6e1a12e26339773e95.jpg",
      "roomid": 526557,
      "roundStatus": 0,
      "broadcast_type": 0,
      "watched_show": {
        "switch": true,
        "num": 0,
        "text_small": "0",
        "text_large": "0人看过",
        "icon": "https://i0.hdslb.com/bfs/live/a725a9e61242ef44d764ac911691a7ce07f36c1d.png",
        "icon_location": "",
        "icon_web": "https://i0.hdslb.com/bfs/live/8d9d0f33ef8bf6f308742752d13dd0df731df19c.png"
      }
    },
    "birthday": "01-01",
    "school": null,
    "profession": {
      "name": "",
      "department": "",
      "title": "",
      "is_show": 0
    },
    "tags": null,
    "series": {
      "user_upgrade_status": 3,
      "show_upgrade_window": false
    },
    "is_senior_member": 0,
    "mcn_info": null,
    "gaia_res_type": 0,
    "gaia_data": null,
    "is_risk": false,
    "elec": {
      "show_info": {
        "show": true,
        "state": 2,
        "title": "充电",
        "icon": "https://i0.hdslb.com/bfs/garb/item/33e2e72d9a0c855f036b4cb55448f44af67a0635.png",
        "jump_url": "https://www.bilibili.com/h5/upower/index?mid=9094311&navhide=1&oid=9094311"
      }
    },
    "contract": null,
    "certificate_show": false
  }
}
```

### 返回结果

|状态码|状态码含义|说明|数据模型|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|成功|Inline|

### 返回数据结构

状态码 **200**

|名称|类型|必选|约束|中文名|说明|
|---|---|---|---|---|---|
|» code|integer|true|none||none|
|» message|string|true|none||none|
|» ttl|integer|true|none||none|
|» data|object|true|none||none|
|»» mid|integer|true|none|用户id|none|
|»» name|string|true|none|用户名|none|
|»» sex|string|true|none|性别|none|
|»» face|string|true|none|头像|none|
|»» face_nft|integer|true|none|NFT头像|none|
|»» face_nft_type|integer|true|none|NFT头像类型|none|
|»» sign|string|true|none|个性签名|none|
|»» rank|integer|true|none|排名|none|
|»» level|integer|true|none|会员等级|none|
|»» jointime|integer|true|none|加入时间|none|
|»» moral|integer|true|none||none|
|»» silence|integer|true|none||none|
|»» coins|integer|true|none|硬币数量|none|
|»» fans_badge|boolean|true|none|粉丝勋章|none|
|»» fans_medal|object|true|none||none|
|»»» show|boolean|true|none||none|
|»»» wear|boolean|true|none||none|
|»»» medal|null|true|none||none|
|»» official|object|true|none|官方认证|none|
|»»» role|integer|true|none||none|
|»»» title|string|true|none||none|
|»»» desc|string|true|none||none|
|»»» type|integer|true|none||none|
|»» vip|object|true|none|大会员信息|none|
|»»» type|integer|true|none||none|
|»»» status|integer|true|none||none|
|»»» due_date|integer|true|none||none|
|»»» vip_pay_type|integer|true|none||none|
|»»» theme_type|integer|true|none||none|
|»»» label|object|true|none||none|
|»»»» path|string|true|none||none|
|»»»» text|string|true|none||none|
|»»»» label_theme|string|true|none||none|
|»»»» text_color|string|true|none||none|
|»»»» bg_style|integer|true|none||none|
|»»»» bg_color|string|true|none||none|
|»»»» border_color|string|true|none||none|
|»»»» use_img_label|boolean|true|none||none|
|»»»» img_label_uri_hans|string|true|none||none|
|»»»» img_label_uri_hant|string|true|none||none|
|»»»» img_label_uri_hans_static|string|true|none||none|
|»»»» img_label_uri_hant_static|string|true|none||none|
|»»» avatar_subscript|integer|true|none||none|
|»»» nickname_color|string|true|none||none|
|»»» role|integer|true|none||none|
|»»» avatar_subscript_url|string|true|none||none|
|»»» tv_vip_status|integer|true|none||none|
|»»» tv_vip_pay_type|integer|true|none||none|
|»»» tv_due_date|integer|true|none||none|
|»» pendant|object|true|none||none|
|»»» pid|integer|true|none||none|
|»»» name|string|true|none||none|
|»»» image|string|true|none||none|
|»»» expire|integer|true|none||none|
|»»» image_enhance|string|true|none||none|
|»»» image_enhance_frame|string|true|none||none|
|»» nameplate|object|true|none||none|
|»»» nid|integer|true|none||none|
|»»» name|string|true|none||none|
|»»» image|string|true|none||none|
|»»» image_small|string|true|none||none|
|»»» level|string|true|none||none|
|»»» condition|string|true|none||none|
|»» user_honour_info|object|true|none||none|
|»»» mid|integer|true|none||none|
|»»» colour|null|true|none||none|
|»»» tags|[string]|true|none||none|
|»» is_followed|boolean|true|none|是否已关注|none|
|»» top_photo|string|true|none||none|
|»» theme|object|true|none||none|
|»» sys_notice|object|true|none||none|
|»» live_room|object|true|none|直播间|none|
|»»» roomStatus|integer|true|none||none|
|»»» liveStatus|integer|true|none||none|
|»»» url|string|true|none||none|
|»»» title|string|true|none||none|
|»»» cover|string|true|none||none|
|»»» roomid|integer|true|none||none|
|»»» roundStatus|integer|true|none||none|
|»»» broadcast_type|integer|true|none||none|
|»»» watched_show|object|true|none||none|
|»»»» switch|boolean|true|none||none|
|»»»» num|integer|true|none||none|
|»»»» text_small|string|true|none||none|
|»»»» text_large|string|true|none||none|
|»»»» icon|string|true|none||none|
|»»»» icon_location|string|true|none||none|
|»»»» icon_web|string|true|none||none|
|»» birthday|string|true|none||none|
|»» school|null|true|none||none|
|»» profession|object|true|none||none|
|»»» name|string|true|none||none|
|»»» department|string|true|none||none|
|»»» title|string|true|none||none|
|»»» is_show|integer|true|none||none|
|»» tags|null|true|none||none|
|»» series|object|true|none||none|
|»»» user_upgrade_status|integer|true|none||none|
|»»» show_upgrade_window|boolean|true|none||none|
|»» is_senior_member|integer|true|none||none|
|»» mcn_info|null|true|none||none|
|»» gaia_res_type|integer|true|none||none|
|»» gaia_data|null|true|none||none|
|»» is_risk|boolean|true|none||none|
|»» elec|object|true|none||none|
|»»» show_info|object|true|none||none|
|»»»» show|boolean|true|none||none|
|»»»» state|integer|true|none||none|
|»»»» title|string|true|none||none|
|»»»» icon|string|true|none||none|
|»»»» jump_url|string|true|none||none|
|»» contract|null|true|none||none|
|»» certificate_show|boolean|true|none||none|

## GET 关注统计

GET /x/relation/stat

### 请求参数

|名称|位置|类型|必选|说明|
|---|---|---|---|---|
|vmid|query|string| 否 |用户id|
|User-Agent|header|string| 否 |none|

> 返回示例

> 200 Response

```json
{}
```

### 返回结果

|状态码|状态码含义|说明|数据模型|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|成功|Inline|

### 返回数据结构

## GET 投稿统计 (需登录)

GET /x/space/upstat

### 请求参数

|名称|位置|类型|必选|说明|
|---|---|---|---|---|
|SESSDATA|cookie|string| 否 |none|
|mid|query|string| 否 |none|
|User-Agent|header|string| 否 |none|

> 返回示例

> 成功

```json
{
  "code": 0,
  "message": "0",
  "ttl": 1,
  "data": {
    "archive": {
      "enable_vt": 0,
      "view": 397426180,
      "vt": 0
    },
    "article": {
      "view": 179528
    },
    "likes": 17977070
  }
}
```

### 返回结果

|状态码|状态码含义|说明|数据模型|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|成功|Inline|

### 返回数据结构

状态码 **200**

|名称|类型|必选|约束|中文名|说明|
|---|---|---|---|---|---|
|» code|integer|true|none||none|
|» message|string|true|none||none|
|» ttl|integer|true|none||none|
|» data|object|true|none||none|
|»» archive|object|true|none||none|
|»»» enable_vt|integer|true|none||none|
|»»» view|integer|true|none||none|
|»»» vt|integer|true|none||none|
|»» article|object|true|none||none|
|»»» view|integer|true|none||none|
|»» likes|integer|true|none||none|

## GET 视频列表

GET /x/space/wbi/arc/search

### 请求参数

|名称|位置|类型|必选|说明|
|---|---|---|---|---|
|mid|query|string| 否 |none|
|ps|query|string| 否 |每页数量|
|tid|query|string| 否 |分类id，0全部|
|special_type|query|string| 否 |none|
|pn|query|string| 否 |当前页码|
|keyword|query|string| 否 |搜索关键词|
|order|query|string| 否 |排序方式，pubdate发布时间, click播放数量, stow收藏数量|
|User-Agent|header|string| 否 |none|

> 返回示例

> 成功

```json
{
  "code": 0,
  "message": "0",
  "ttl": 1,
  "data": {
    "list": {
      "tlist": {
        "1": {
          "tid": 1,
          "count": 652,
          "name": "动画"
        },
        "4": {
          "tid": 4,
          "count": 1,
          "name": "游戏"
        },
        "160": {
          "tid": 160,
          "count": 1,
          "name": "生活"
        },
        "181": {
          "tid": 181,
          "count": 1,
          "name": "影视"
        }
      },
      "vlist": [
        {
          "comment": 13441,
          "typeid": 253,
          "play": 3709213,
          "pic": "http://i0.hdslb.com/bfs/archive/b8be7d519db17b2f7d165197635794b51171d4fa.jpg",
          "subtitle": "",
          "description": "凯老师：最后一课开始了！\n\n有趣的视频推荐：\n《海贼王最终秘密：乔伊·波伊完整分析》BV15i4y1277p\n《路飞五档与天落九影》BV1AF41147LA\n《海贼王动画幕后故事》BV1iy4y1T7et\n《探秘“天王”乌拉诺斯》BV1so4y1U7CZ\n《23年动画片头曲大合集》BV1wh411W7Mg\n《海贼王漫画结局猜想》BV1B64y1q7nL",
          "copyright": "1",
          "title": "海贼王1044话完整解说：路飞5档正式开启！继承太阳神尼卡的意志，揭晓世界黎明的希望！欢笑传说从未结束！",
          "review": 0,
          "author": "动漫作业本",
          "mid": 488779255,
          "created": 1648204247,
          "length": "08:24",
          "video_review": 8072,
          "aid": 682571407,
          "bvid": "BV1cU4y1o7WE",
          "hide_click": false,
          "is_pay": 0,
          "is_union_video": 0,
          "is_steins_gate": 0,
          "is_live_playback": 0,
          "meta": {
            "id": 2658,
            "title": "【燃到冒烟】海贼王最新漫画动态解说！",
            "cover": "https://i0.hdslb.com/bfs/archive/f58dc256d3a61799af922742446593e7db1ec9e8.jpg",
            "mid": 488779255,
            "intro": "海贼王每周漫画解说，原滋原味还原每一份热血与感动！",
            "sign_state": 0,
            "attribute": 140,
            "stat": {
              "season_id": 2658,
              "view": 104526435,
              "danmaku": 292605,
              "reply": 219652,
              "favorite": 271164,
              "coin": 905601,
              "share": 201788,
              "like": 3558973,
              "mtime": 1697897786,
              "vt": 0,
              "vv": 0
            },
            "ep_count": 96,
            "first_aid": 330939965,
            "ptime": 1697084650,
            "ep_num": 96
          },
          "is_avoided": 0,
          "attribute": 0,
          "is_charging_arc": false,
          "vt": 0,
          "enable_vt": 0,
          "vt_display": "",
          "playback_position": 0
        },
        {
          "comment": 27731,
          "typeid": 253,
          "play": 3516017,
          "pic": "http://i2.hdslb.com/bfs/archive/e6982b94d3e6e0cdc84f84a388f631b8d6967917.jpg",
          "subtitle": "",
          "description": "凯老师，再战300回合！\n\n有趣的视频推荐：\n《海贼王最终秘密：乔伊·波伊完整分析》BV15i4y1277p\n《路飞五档与天落九影》BV1AF41147LA\n《海贼王动画幕后故事》BV1iy4y1T7et\n《探秘“天王”乌拉诺斯》BV1so4y1U7CZ\n《23年动画片头曲大合集》BV1wh411W7Mg\n《海贼王漫画结局猜想》BV1B64y1q7nL",
          "copyright": "1",
          "title": "海贼王1044话情报来了！人人果实·幻兽种·尼卡型态！5档路飞能力全面觉醒，幻兽种果实再添新设定！",
          "review": 0,
          "author": "动漫作业本",
          "mid": 488779255,
          "created": 1647952998,
          "length": "01:46",
          "video_review": 3533,
          "aid": 509969815,
          "bvid": "BV1tu411q72h",
          "hide_click": false,
          "is_pay": 0,
          "is_union_video": 0,
          "is_steins_gate": 0,
          "is_live_playback": 0,
          "meta": null,
          "is_avoided": 0,
          "attribute": 0,
          "is_charging_arc": false,
          "vt": 0,
          "enable_vt": 0,
          "vt_display": "",
          "playback_position": 0
        },
        {
          "comment": 6476,
          "typeid": 253,
          "play": 2890236,
          "pic": "http://i0.hdslb.com/bfs/archive/3680389b16296a6297c9a16a3d9a6357656c374a.jpg",
          "subtitle": "",
          "description": "路飞：我的快乐，在你之上！\n\n有趣的视频推荐：\n《海贼王最终秘密：乔伊·波伊完整分析》BV15i4y1277p\n《路飞五档与天落九影》BV1AF41147LA\n《海贼王动画幕后故事》BV1iy4y1T7et\n《探秘“天王”乌拉诺斯》BV1so4y1U7CZ\n《23年动画片头曲大合集》BV1wh411W7Mg\n《海贼王漫画结局猜想》BV1B64y1q7nL",
          "copyright": "1",
          "title": "海贼王1045话完整解说：5档路飞大显神威！魔王凯多疯狂乱斗！鬼岛屋顶上演惊天对决！",
          "review": 0,
          "author": "动漫作业本",
          "mid": 488779255,
          "created": 1648809239,
          "length": "08:01",
          "video_review": 6669,
          "aid": 640295592,
          "bvid": "BV1MY4y1W7bA",
          "hide_click": false,
          "is_pay": 0,
          "is_union_video": 0,
          "is_steins_gate": 0,
          "is_live_playback": 0,
          "meta": {
            "id": 2658,
            "title": "【燃到冒烟】海贼王最新漫画动态解说！",
            "cover": "https://i0.hdslb.com/bfs/archive/f58dc256d3a61799af922742446593e7db1ec9e8.jpg",
            "mid": 488779255,
            "intro": "海贼王每周漫画解说，原滋原味还原每一份热血与感动！",
            "sign_state": 0,
            "attribute": 140,
            "stat": {
              "season_id": 2658,
              "view": 104526446,
              "danmaku": 292605,
              "reply": 219652,
              "favorite": 271164,
              "coin": 905601,
              "share": 201788,
              "like": 3558973,
              "mtime": 1697897788,
              "vt": 0,
              "vv": 0
            },
            "ep_count": 96,
            "first_aid": 330939965,
            "ptime": 1697084650,
            "ep_num": 96
          },
          "is_avoided": 0,
          "attribute": 0,
          "is_charging_arc": false,
          "vt": 0,
          "enable_vt": 0,
          "vt_display": "",
          "playback_position": 0
        },
        {
          "comment": 6554,
          "typeid": 253,
          "play": 2889638,
          "pic": "http://i1.hdslb.com/bfs/archive/410543c1e06b62fa3f836b3c01a5e6a94356d523.jpg",
          "subtitle": "",
          "description": "绿牛：鸟语花香的正义！\n\n视频BGM（部分）：\n宾克斯的美酒（草帽团合唱版）\n\n图片来源说明：\n视频内容及封面使用的图片素材来自于网络搜集，素材不作为商业用途，版权归属于原创作者，仅供交流学习，部分图片来源无法考证，如有问题请务必直接与我联系！\n\n有趣的视频推荐：\n《海贼王最终秘密：乔伊·波伊完整分析》BV15i4y1277p\n《路飞五档与天落九影》BV1AF41147LA\n《海贼王动画幕后故事》BV1iy4y1T7et\n《探秘“天王”乌拉诺斯》BV1so4y1U7CZ\n《海贼王尾田创作史》BV1tS4y",
          "copyright": "1",
          "title": "海贼王1053话完整解说：新的四皇震惊大海！最高战力危机四伏！和之国终极宴会开幕，古代兵器冥王揭晓秘密！",
          "review": 0,
          "author": "动漫作业本",
          "mid": 488779255,
          "created": 1655464398,
          "length": "09:10",
          "video_review": 7569,
          "aid": 642603011,
          "bvid": "BV1vY4y1g7DK",
          "hide_click": false,
          "is_pay": 0,
          "is_union_video": 0,
          "is_steins_gate": 0,
          "is_live_playback": 0,
          "meta": {
            "id": 2658,
            "title": "【燃到冒烟】海贼王最新漫画动态解说！",
            "cover": "https://i0.hdslb.com/bfs/archive/f58dc256d3a61799af922742446593e7db1ec9e8.jpg",
            "mid": 488779255,
            "intro": "海贼王每周漫画解说，原滋原味还原每一份热血与感动！",
            "sign_state": 0,
            "attribute": 140,
            "stat": {
              "season_id": 2658,
              "view": 104526446,
              "danmaku": 292605,
              "reply": 219652,
              "favorite": 271164,
              "coin": 905601,
              "share": 201788,
              "like": 3558973,
              "mtime": 1697897788,
              "vt": 0,
              "vv": 0
            },
            "ep_count": 96,
            "first_aid": 330939965,
            "ptime": 1697084650,
            "ep_num": 96
          },
          "is_avoided": 0,
          "attribute": 0,
          "is_charging_arc": false,
          "vt": 0,
          "enable_vt": 0,
          "vt_display": "",
          "playback_position": 0
        },
        {
          "comment": 4840,
          "typeid": 253,
          "play": 2673556,
          "pic": "http://i0.hdslb.com/bfs/archive/0e14c5bb87f496eefb20b50466cdb2ec4d0a55bb.jpg",
          "subtitle": "",
          "description": "橡胶为什么不怕火焰？靠毅力！\n\n有趣的视频推荐：\n《海贼王最终秘密：乔伊·波伊完整分析》BV15i4y1277p\n《路飞五档与天落九影》BV1AF41147LA\n《海贼王动画幕后故事》BV1iy4y1T7et\n《探秘“天王”乌拉诺斯》BV1so4y1U7CZ\n《23年动画片头曲大合集》BV1wh411W7Mg\n《海贼王漫画结局猜想》BV1B64y1q7nL",
          "copyright": "1",
          "title": "五档路飞觉醒终极猜想！揭开橡胶果实变形之谜！跨越500话的伏笔，被继承的火焰，将会如何战胜凯多？",
          "review": 0,
          "author": "动漫作业本",
          "mid": 488779255,
          "created": 1647427965,
          "length": "13:52",
          "video_review": 6731,
          "aid": 767320402,
          "bvid": "BV1nr4y1i7Wy",
          "hide_click": false,
          "is_pay": 0,
          "is_union_video": 0,
          "is_steins_gate": 0,
          "is_live_playback": 0,
          "meta": {
            "id": 74265,
            "title": "【细思极恐】海贼王细节伏笔分析！",
            "cover": "https://archive.biliimg.com/bfs/archive/c33230e2544c3e01090a2be3a2ff2d22b1d9817c.jpg",
            "mid": 488779255,
            "intro": "每周漫画剧情细节与伏笔分析！挖掘那些尾田留下的线索",
            "sign_state": 0,
            "attribute": 140,
            "stat": {
              "season_id": 74265,
              "view": 65523584,
              "danmaku": 199513,
              "reply": 143630,
              "favorite": 237371,
              "coin": 740254,
              "share": 104505,
              "like": 2716267,
              "mtime": 1697897783,
              "vt": 0,
              "vv": 0
            },
            "ep_count": 90,
            "first_aid": 850804006,
            "ptime": 1697537289,
            "ep_num": 90
          },
          "is_avoided": 0,
          "attribute": 0,
          "is_charging_arc": false,
          "vt": 0,
          "enable_vt": 0,
          "vt_display": "",
          "playback_position": 0
        },
        {
          "comment": 3772,
          "typeid": 253,
          "play": 2312968,
          "pic": "http://i1.hdslb.com/bfs/archive/585135c490c11bd7020005a531daba2e709b77d0.jpg",
          "subtitle": "",
          "description": "在古代，四皇就是这样诞生的！\n\n图片来源说明：\n视频内容及封面使用的图片素材来自于网络搜集，素材不作为商业用途，版权归属于原创作者，仅供交流学习，部分图片来源无法考证，如有问题请务必直接与我联系！\n\n有趣的视频推荐：\n《海贼王最终秘密：乔伊·波伊完整分析》BV15i4y1277p\n《路飞五档与天落九影》BV1AF41147LA\n《海贼王动画幕后故事》BV1iy4y1T7et\n《探秘“天王”乌拉诺斯》BV1so4y1U7CZ",
          "copyright": "1",
          "title": "海贼王1058话完整解说：大海皇帝难逃一劫！草帽赏金全员飙升！革命军再次集合，炎帝萨博的行动！",
          "review": 0,
          "author": "动漫作业本",
          "mid": 488779255,
          "created": 1661509559,
          "length": "11:25",
          "video_review": 6431,
          "aid": 772446988,
          "bvid": "BV1d14y1x7u2",
          "hide_click": false,
          "is_pay": 0,
          "is_union_video": 0,
          "is_steins_gate": 0,
          "is_live_playback": 0,
          "meta": {
            "id": 2658,
            "title": "【燃到冒烟】海贼王最新漫画动态解说！",
            "cover": "https://i0.hdslb.com/bfs/archive/f58dc256d3a61799af922742446593e7db1ec9e8.jpg",
            "mid": 488779255,
            "intro": "海贼王每周漫画解说，原滋原味还原每一份热血与感动！",
            "sign_state": 0,
            "attribute": 140,
            "stat": {
              "season_id": 2658,
              "view": 104526446,
              "danmaku": 292605,
              "reply": 219652,
              "favorite": 271164,
              "coin": 905601,
              "share": 201788,
              "like": 3558973,
              "mtime": 1697897788,
              "vt": 0,
              "vv": 0
            },
            "ep_count": 96,
            "first_aid": 330939965,
            "ptime": 1697084650,
            "ep_num": 96
          },
          "is_avoided": 0,
          "attribute": 0,
          "is_charging_arc": false,
          "vt": 0,
          "enable_vt": 0,
          "vt_display": "",
          "playback_position": 0
        },
        {
          "comment": 6101,
          "typeid": 253,
          "play": 2147589,
          "pic": "http://i0.hdslb.com/bfs/archive/8aa15ed25ea0d84ab6d9d9a2c711123d86d447d0.jpg",
          "subtitle": "",
          "description": "路飞：帝王引擎，发动！\n\n有趣的视频推荐：\n《海贼王最终秘密：乔伊·波伊完整分析》BV15i4y1277p\n《路飞五档与天落九影》BV1AF41147LA\n《海贼王动画幕后故事》BV1iy4y1T7et\n《探秘“天王”乌拉诺斯》BV1so4y1U7CZ\n《23年动画片头曲大合集》BV1wh411W7Mg\n《海贼王漫画结局猜想》BV1B64y1q7nL",
          "copyright": "1",
          "title": "空白100年战争终极猜想！失去“声音”的乔伊波伊，与重生的太阳神之力！人人果实幻兽种能力大盘点！",
          "review": 0,
          "author": "动漫作业本",
          "mid": 488779255,
          "created": 1648462339,
          "length": "16:44",
          "video_review": 6885,
          "aid": 595216246,
          "bvid": "BV1Dq4y1Y7rx",
          "hide_click": false,
          "is_pay": 0,
          "is_union_video": 0,
          "is_steins_gate": 0,
          "is_live_playback": 0,
          "meta": {
            "id": 74265,
            "title": "【细思极恐】海贼王细节伏笔分析！",
            "cover": "https://archive.biliimg.com/bfs/archive/c33230e2544c3e01090a2be3a2ff2d22b1d9817c.jpg",
            "mid": 488779255,
            "intro": "每周漫画剧情细节与伏笔分析！挖掘那些尾田留下的线索",
            "sign_state": 0,
            "attribute": 140,
            "stat": {
              "season_id": 74265,
              "view": 65523584,
              "danmaku": 199513,
              "reply": 143630,
              "favorite": 237371,
              "coin": 740254,
              "share": 104505,
              "like": 2716267,
              "mtime": 1697897783,
              "vt": 0,
              "vv": 0
            },
            "ep_count": 90,
            "first_aid": 850804006,
            "ptime": 1697537289,
            "ep_num": 90
          },
          "is_avoided": 0,
          "attribute": 0,
          "is_charging_arc": false,
          "vt": 0,
          "enable_vt": 0,
          "vt_display": "",
          "playback_position": 0
        },
        {
          "comment": 4470,
          "typeid": 253,
          "play": 2144893,
          "pic": "http://i0.hdslb.com/bfs/archive/1bca7e020a3276c1e693ad52b6c25f32e1a16a7d.jpg",
          "subtitle": "",
          "description": "一顶草帽开启的传说！\n\n有趣的视频推荐：\n《海贼王动画幕后故事》BV1iy4y1T7et\n《探秘“天王”乌拉诺斯》BV1so4y1U7CZ\n《23年动画片头曲大合集》BV1wh411W7Mg\n《海贼王漫画结局猜想》BV1B64y1q7nL\n《路飞vs凯多！1036话完整解说》BV18r4y1S7GD",
          "copyright": "1",
          "title": "海贼王最终秘密：乔伊·波伊完整分析！6处伏笔揭开隐藏的欢笑传说！太阳神尼卡与世界黎明的关联",
          "review": 0,
          "author": "动漫作业本",
          "mid": 488779255,
          "created": 1645440917,
          "length": "14:43",
          "video_review": 5966,
          "aid": 551685467,
          "bvid": "BV15i4y1277p",
          "hide_click": false,
          "is_pay": 0,
          "is_union_video": 0,
          "is_steins_gate": 0,
          "is_live_playback": 0,
          "meta": {
            "id": 74265,
            "title": "【细思极恐】海贼王细节伏笔分析！",
            "cover": "https://archive.biliimg.com/bfs/archive/c33230e2544c3e01090a2be3a2ff2d22b1d9817c.jpg",
            "mid": 488779255,
            "intro": "每周漫画剧情细节与伏笔分析！挖掘那些尾田留下的线索",
            "sign_state": 0,
            "attribute": 140,
            "stat": {
              "season_id": 74265,
              "view": 65523584,
              "danmaku": 199513,
              "reply": 143630,
              "favorite": 237371,
              "coin": 740254,
              "share": 104505,
              "like": 2716267,
              "mtime": 1697897783,
              "vt": 0,
              "vv": 0
            },
            "ep_count": 90,
            "first_aid": 850804006,
            "ptime": 1697537289,
            "ep_num": 90
          },
          "is_avoided": 0,
          "attribute": 0,
          "is_charging_arc": false,
          "vt": 0,
          "enable_vt": 0,
          "vt_display": "",
          "playback_position": 0
        },
        {
          "comment": 2185,
          "typeid": 253,
          "play": 2092180,
          "pic": "http://i1.hdslb.com/bfs/archive/99f133a9b354f0c197ba1b3411ca915f313ab1eb.jpg",
          "subtitle": "",
          "description": "",
          "copyright": "1",
          "title": "对不起，我要开始吹了！海贼王982集到底有多精彩？来看看这一集被海米吹爆的动画幕后的故事",
          "review": 0,
          "author": "动漫作业本",
          "mid": 488779255,
          "created": 1626286147,
          "length": "04:47",
          "video_review": 1589,
          "aid": 804246386,
          "bvid": "BV1iy4y1T7et",
          "hide_click": false,
          "is_pay": 0,
          "is_union_video": 0,
          "is_steins_gate": 0,
          "is_live_playback": 0,
          "meta": null,
          "is_avoided": 0,
          "attribute": 0,
          "is_charging_arc": false,
          "vt": 0,
          "enable_vt": 0,
          "vt_display": "",
          "playback_position": 0
        },
        {
          "comment": 3326,
          "typeid": 253,
          "play": 2059824,
          "pic": "http://i0.hdslb.com/bfs/archive/af61e69c8512578505165151335950f7c73bfd9c.jpg",
          "subtitle": "",
          "description": "凯多：下课了！！\n\n视频BGM（部分）：\nMad-Nug\nBreathing\nLuffy's Fierce Attack!\n\n图片来源说明：\n视频内容及封面使用的图片素材来自于网络搜集，素材不作为商业用途，版权归属于原创作者，仅供交流学习，部分图片来源无法考证，如有问题请务必直接与我联系！\n\n有趣的视频推荐：\n《海贼王最终秘密：乔伊·波伊完整分析》BV15i4y1277p\n《路飞五档与天落九影》BV1AF41147LA\n《海贼王动画幕后故事》BV1iy4y1T7et\n《探秘“天王”乌拉诺斯》BV1so4y",
          "copyright": "1",
          "title": "海贼王1049话完整解说：雷霆一击决胜凯多！百兽之王回忆双杀！从天际陨落的巨龙，从黑暗破晓的国度，鬼岛决战迎来最后！",
          "review": 0,
          "author": "动漫作业本",
          "mid": 488779255,
          "created": 1652436185,
          "length": "08:08",
          "video_review": 7724,
          "aid": 341512757,
          "bvid": "BV1RR4y1A7cs",
          "hide_click": false,
          "is_pay": 0,
          "is_union_video": 0,
          "is_steins_gate": 0,
          "is_live_playback": 0,
          "meta": {
            "id": 2658,
            "title": "【燃到冒烟】海贼王最新漫画动态解说！",
            "cover": "https://i0.hdslb.com/bfs/archive/f58dc256d3a61799af922742446593e7db1ec9e8.jpg",
            "mid": 488779255,
            "intro": "海贼王每周漫画解说，原滋原味还原每一份热血与感动！",
            "sign_state": 0,
            "attribute": 140,
            "stat": {
              "season_id": 2658,
              "view": 104526446,
              "danmaku": 292605,
              "reply": 219652,
              "favorite": 271164,
              "coin": 905601,
              "share": 201788,
              "like": 3558973,
              "mtime": 1697897788,
              "vt": 0,
              "vv": 0
            },
            "ep_count": 96,
            "first_aid": 330939965,
            "ptime": 1697084650,
            "ep_num": 96
          },
          "is_avoided": 0,
          "attribute": 0,
          "is_charging_arc": false,
          "vt": 0,
          "enable_vt": 0,
          "vt_display": "",
          "playback_position": 0
        },
        {
          "comment": 3037,
          "typeid": 253,
          "play": 2023078,
          "pic": "http://i1.hdslb.com/bfs/archive/cd2d241f4257f072b258ffdd784cd52c9c50dd0d.jpg",
          "subtitle": "",
          "description": "甚平：看我一波带走！！\n\n有趣的视频推荐：\n《海贼王最终秘密：乔伊·波伊完整分析》BV15i4y1277p\n《路飞五档与天落九影》BV1AF41147LA\n《海贼王动画幕后故事》BV1iy4y1T7et\n《探秘“天王”乌拉诺斯》BV1so4y1U7CZ\n《23年动画片头曲大合集》BV1wh411W7Mg\n《海贼王漫画结局猜想》BV1B64y1q7nL",
          "copyright": "1",
          "title": "海贼王1046话完整解说：天雷成剑大战凯多！五档路飞上演神技！海侠甚平联手忍者雷藏，降伏绝境火海！",
          "review": 0,
          "author": "动漫作业本",
          "mid": 488779255,
          "created": 1649413150,
          "length": "08:12",
          "video_review": 4318,
          "aid": 640552752,
          "bvid": "BV1yY4y1H7Ei",
          "hide_click": false,
          "is_pay": 0,
          "is_union_video": 0,
          "is_steins_gate": 0,
          "is_live_playback": 0,
          "meta": {
            "id": 2658,
            "title": "【燃到冒烟】海贼王最新漫画动态解说！",
            "cover": "https://i0.hdslb.com/bfs/archive/f58dc256d3a61799af922742446593e7db1ec9e8.jpg",
            "mid": 488779255,
            "intro": "海贼王每周漫画解说，原滋原味还原每一份热血与感动！",
            "sign_state": 0,
            "attribute": 140,
            "stat": {
              "season_id": 2658,
              "view": 104526446,
              "danmaku": 292605,
              "reply": 219652,
              "favorite": 271164,
              "coin": 905601,
              "share": 201788,
              "like": 3558973,
              "mtime": 1697897788,
              "vt": 0,
              "vv": 0
            },
            "ep_count": 96,
            "first_aid": 330939965,
            "ptime": 1697084650,
            "ep_num": 96
          },
          "is_avoided": 0,
          "attribute": 0,
          "is_charging_arc": false,
          "vt": 0,
          "enable_vt": 0,
          "vt_display": "",
          "playback_position": 0
        },
        {
          "comment": 4168,
          "typeid": 253,
          "play": 1915699,
          "pic": "http://i1.hdslb.com/bfs/archive/35169185593d4e930ba6035ac031caae0243decd.jpg",
          "subtitle": "",
          "description": "凯多：这座岛屿就由我来守护！！\n\n有趣的视频推荐：\n《海贼王最终秘密：乔伊·波伊完整分析》BV15i4y1277p\n《路飞五档与天落九影》BV1AF41147LA\n《海贼王动画幕后故事》BV1iy4y1T7et\n《探秘“天王”乌拉诺斯》BV1so4y1U7CZ\n《23年动画片头曲大合集》BV1wh411W7Mg\n《海贼王漫画结局猜想》BV1B64y1q7nL",
          "copyright": "1",
          "title": "海贼王1047话完整解说：流星陨石神王降临！百兽之王力劈雷霆！命运交织的恶鬼之岛，即将迎来最终崩盘！",
          "review": 0,
          "author": "动漫作业本",
          "mid": 488779255,
          "created": 1650621513,
          "length": "08:20",
          "video_review": 4794,
          "aid": 768491667,
          "bvid": "BV1Dr4y1J7CM",
          "hide_click": false,
          "is_pay": 0,
          "is_union_video": 0,
          "is_steins_gate": 0,
          "is_live_playback": 0,
          "meta": {
            "id": 2658,
            "title": "【燃到冒烟】海贼王最新漫画动态解说！",
            "cover": "https://i0.hdslb.com/bfs/archive/f58dc256d3a61799af922742446593e7db1ec9e8.jpg",
            "mid": 488779255,
            "intro": "海贼王每周漫画解说，原滋原味还原每一份热血与感动！",
            "sign_state": 0,
            "attribute": 140,
            "stat": {
              "season_id": 2658,
              "view": 104526446,
              "danmaku": 292605,
              "reply": 219652,
              "favorite": 271164,
              "coin": 905601,
              "share": 201788,
              "like": 3558973,
              "mtime": 1697897788,
              "vt": 0,
              "vv": 0
            },
            "ep_count": 96,
            "first_aid": 330939965,
            "ptime": 1697084650,
            "ep_num": 96
          },
          "is_avoided": 0,
          "attribute": 0,
          "is_charging_arc": false,
          "vt": 0,
          "enable_vt": 0,
          "vt_display": "",
          "playback_position": 0
        },
        {
          "comment": 1264,
          "typeid": 253,
          "play": 1911775,
          "pic": "http://i0.hdslb.com/bfs/archive/b7011742949067f3176db8dc84d8d3bb7a8f5e20.jpg",
          "subtitle": "",
          "description": "",
          "copyright": "1",
          "title": "海贼王1036话全图情报：凯多也是乔伊波伊？索隆加冕地狱之王，鬼岛战线超级大回顾！",
          "review": 0,
          "author": "动漫作业本",
          "mid": 488779255,
          "created": 1640348803,
          "length": "03:23",
          "video_review": 603,
          "aid": 592592735,
          "bvid": "BV1sq4y1m7QF",
          "hide_click": false,
          "is_pay": 0,
          "is_union_video": 0,
          "is_steins_gate": 0,
          "is_live_playback": 0,
          "meta": {
            "id": 64412,
            "title": "【海鸥送报】海贼王每周最新情报！",
            "cover": "https://archive.biliimg.com/bfs/archive/3c25061d2cdaacac709377a18a33ba78e32d0b35.jpg",
            "mid": 488779255,
            "intro": "每周第一时间更新海贼王漫画最新情报，欢迎订阅",
            "sign_state": 0,
            "attribute": 140,
            "stat": {
              "season_id": 64412,
              "view": 109989520,
              "danmaku": 156955,
              "reply": 383762,
              "favorite": 142920,
              "coin": 362220,
              "share": 320353,
              "like": 3864880,
              "mtime": 1697897782,
              "vt": 0,
              "vv": 0
            },
            "ep_count": 166,
            "first_aid": 592592735,
            "ptime": 1697009301,
            "ep_num": 166
          },
          "is_avoided": 0,
          "attribute": 0,
          "is_charging_arc": false,
          "vt": 0,
          "enable_vt": 0,
          "vt_display": "",
          "playback_position": 0
        },
        {
          "comment": 4797,
          "typeid": 253,
          "play": 1855771,
          "pic": "http://i1.hdslb.com/bfs/archive/cb8e3d6d0677bd40672b19c48003b03765b9b892.jpg",
          "subtitle": "",
          "description": "见闻色都得给面子！\n\n图片来源说明：\n视频内容及封面使用的图片素材来自于网络搜集，素材不作为商业用途，版权归属于原创作者，仅供交流学习，部分图片来源无法考证，如有问题请务必直接与我联系！\n\n有趣的视频推荐：\n《海贼王最终秘密：乔伊·波伊完整分析》BV15i4y1277p\n《路飞五档与天落九影》BV1AF41147LA\n《海贼王动画幕后故事》BV1iy4y1T7et\n《探秘“天王”乌拉诺斯》BV1so4y1U7CZ\n《海贼王尾田创作史》BV1tS4y",
          "copyright": "1",
          "title": "霸王色见闻杀！香克斯又一绝技曝光！红发海贼团设定完整解读！最神秘的四皇团，最平衡的铁壁团，开始发力！",
          "review": 0,
          "author": "动漫作业本",
          "mid": 488779255,
          "created": 1659852595,
          "length": "05:26",
          "video_review": 4175,
          "aid": 644188982,
          "bvid": "BV11Y4y1w7R3",
          "hide_click": false,
          "is_pay": 0,
          "is_union_video": 0,
          "is_steins_gate": 0,
          "is_live_playback": 0,
          "meta": {
            "id": 426614,
            "title": "【海式漫谈】讲好每一个漫画细节",
            "cover": "https://archive.biliimg.com/bfs/archive/58575d184c1a996d1ab0a4a54b48af0577479e21.jpg",
            "mid": 488779255,
            "intro": "独特的漫画分析系列，每期针对一个细分主题，讲好故事",
            "sign_state": 0,
            "attribute": 140,
            "stat": {
              "season_id": 426614,
              "view": 43093934,
              "danmaku": 85641,
              "reply": 71613,
              "favorite": 139548,
              "coin": 183617,
              "share": 52435,
              "like": 1702071,
              "mtime": 1697897783,
              "vt": 0,
              "vv": 0
            },
            "ep_count": 58,
            "first_aid": 769237776,
            "ptime": 1697797549,
            "ep_num": 58
          },
          "is_avoided": 0,
          "attribute": 0,
          "is_charging_arc": false,
          "vt": 0,
          "enable_vt": 0,
          "vt_display": "",
          "playback_position": 0
        },
        {
          "comment": 3932,
          "typeid": 253,
          "play": 1852262,
          "pic": "http://i0.hdslb.com/bfs/archive/e54db91ddcf299d5aa67008e2c4715496cf9c527.jpg",
          "subtitle": "",
          "description": "雷利：给我一个面子...\n\n图片来源说明：\n视频内容及封面使用的图片素材来自于网络搜集，素材不作为商业用途，版权归属于原创作者，仅供交流学习，部分图片来源无法考证，如有问题请务必直接与我联系！\n\n有趣的视频推荐：\n《海贼王最终秘密：乔伊·波伊完整分析》BV15i4y1277p\n《路飞五档与天落九影》BV1AF41147LA\n《海贼王动画幕后故事》BV1iy4y1T7et\n《探秘“天王”乌拉诺斯》BV1so4y1U7CZ\n《海贼王尾田创作史》BV1tS4y1w7YY",
          "copyright": "1",
          "title": "海贼王1059话完整解说：最强兵器神之裁决！冥王雷利反击黑暗！四皇七武海与海军英雄的大乱战！",
          "review": 0,
          "author": "动漫作业本",
          "mid": 488779255,
          "created": 1662720316,
          "length": "11:07",
          "video_review": 6448,
          "aid": 645335484,
          "bvid": "BV1BY4y1M7BD",
          "hide_click": false,
          "is_pay": 0,
          "is_union_video": 0,
          "is_steins_gate": 0,
          "is_live_playback": 0,
          "meta": {
            "id": 2658,
            "title": "【燃到冒烟】海贼王最新漫画动态解说！",
            "cover": "https://i0.hdslb.com/bfs/archive/f58dc256d3a61799af922742446593e7db1ec9e8.jpg",
            "mid": 488779255,
            "intro": "海贼王每周漫画解说，原滋原味还原每一份热血与感动！",
            "sign_state": 0,
            "attribute": 140,
            "stat": {
              "season_id": 2658,
              "view": 104526446,
              "danmaku": 292605,
              "reply": 219652,
              "favorite": 271164,
              "coin": 905601,
              "share": 201788,
              "like": 3558973,
              "mtime": 1697897788,
              "vt": 0,
              "vv": 0
            },
            "ep_count": 96,
            "first_aid": 330939965,
            "ptime": 1697084650,
            "ep_num": 96
          },
          "is_avoided": 0,
          "attribute": 0,
          "is_charging_arc": false,
          "vt": 0,
          "enable_vt": 0,
          "vt_display": "",
          "playback_position": 0
        },
        {
          "comment": 2081,
          "typeid": 253,
          "play": 1816855,
          "pic": "http://i1.hdslb.com/bfs/archive/9d7e17023b6d124b5d0da4997d8658c99eb6d62e.jpg",
          "subtitle": "",
          "description": "路飞：感谢爷爷，让我长大\n\n图片来源说明：\n视频内容及封面使用的图片素材来自于网络搜集，素材不作为商业用途，版权归属于原创作者，仅供交流学习，部分图片来源无法考证，如有问题请务必直接与我联系！\n\n有趣的视频推荐：\n《海贼王最终秘密：乔伊·波伊完整分析》BV15i4y1277p\n《海贼王动画幕后故事》BV1iy4y1T7et\n《探秘“天王”乌拉诺斯》BV1so4y1U7CZ\n《海贼王尾田创作史》BV1tS4y1w7YY",
          "copyright": "1",
          "title": "卡普是“宇宙级”战力？黑胡子蒂奇到底有什么计划？详解5颗全新恶魔果实能力，海贼王1080话细节伏笔分析！",
          "review": 0,
          "author": "动漫作业本",
          "mid": 488779255,
          "created": 1681221845,
          "length": "13:57",
          "video_review": 3746,
          "aid": 782327346,
          "bvid": "BV1L24y1w72t",
          "hide_click": false,
          "is_pay": 0,
          "is_union_video": 0,
          "is_steins_gate": 0,
          "is_live_playback": 0,
          "meta": {
            "id": 74265,
            "title": "【细思极恐】海贼王细节伏笔分析！",
            "cover": "https://archive.biliimg.com/bfs/archive/c33230e2544c3e01090a2be3a2ff2d22b1d9817c.jpg",
            "mid": 488779255,
            "intro": "每周漫画剧情细节与伏笔分析！挖掘那些尾田留下的线索",
            "sign_state": 0,
            "attribute": 140,
            "stat": {
              "season_id": 74265,
              "view": 65523584,
              "danmaku": 199513,
              "reply": 143630,
              "favorite": 237371,
              "coin": 740254,
              "share": 104505,
              "like": 2716267,
              "mtime": 1697897783,
              "vt": 0,
              "vv": 0
            },
            "ep_count": 90,
            "first_aid": 850804006,
            "ptime": 1697537289,
            "ep_num": 90
          },
          "is_avoided": 0,
          "attribute": 0,
          "is_charging_arc": false,
          "vt": 0,
          "enable_vt": 0,
          "vt_display": "",
          "playback_position": 0
        },
        {
          "comment": 2681,
          "typeid": 253,
          "play": 1790786,
          "pic": "http://i1.hdslb.com/bfs/archive/112dcc2c32f84c8c12cbd4cd878ef31b10705727.jpg",
          "subtitle": "",
          "description": "",
          "copyright": "1",
          "title": "海贼王1033话完整解说：索隆霸王色霸气觉醒！迈向顶级剑豪的力量！霜月一脉因缘际会，三把名刀成就传说！",
          "review": 0,
          "author": "动漫作业本",
          "mid": 488779255,
          "created": 1637927372,
          "length": "08:36",
          "video_review": 2620,
          "aid": 251907845,
          "bvid": "BV14Y41147DG",
          "hide_click": false,
          "is_pay": 0,
          "is_union_video": 0,
          "is_steins_gate": 0,
          "is_live_playback": 0,
          "meta": {
            "id": 2658,
            "title": "【燃到冒烟】海贼王最新漫画动态解说！",
            "cover": "https://i0.hdslb.com/bfs/archive/f58dc256d3a61799af922742446593e7db1ec9e8.jpg",
            "mid": 488779255,
            "intro": "海贼王每周漫画解说，原滋原味还原每一份热血与感动！",
            "sign_state": 0,
            "attribute": 140,
            "stat": {
              "season_id": 2658,
              "view": 104526446,
              "danmaku": 292605,
              "reply": 219652,
              "favorite": 271164,
              "coin": 905601,
              "share": 201788,
              "like": 3558973,
              "mtime": 1697897788,
              "vt": 0,
              "vv": 0
            },
            "ep_count": 96,
            "first_aid": 330939965,
            "ptime": 1697084650,
            "ep_num": 96
          },
          "is_avoided": 0,
          "attribute": 0,
          "is_charging_arc": false,
          "vt": 0,
          "enable_vt": 0,
          "vt_display": "",
          "playback_position": 0
        },
        {
          "comment": 3653,
          "typeid": 253,
          "play": 1790289,
          "pic": "http://i1.hdslb.com/bfs/archive/d3c58722ce587d33db24639baec47365e9871300.jpg",
          "subtitle": "",
          "description": "",
          "copyright": "1",
          "title": "盘点海贼王23年全部片头曲，其中4个已成绝唱！一口气看完全部动画经典OP",
          "review": 0,
          "author": "动漫作业本",
          "mid": 488779255,
          "created": 1631699783,
          "length": "51:02",
          "video_review": 25122,
          "aid": 208124481,
          "bvid": "BV1wh411W7Mg",
          "hide_click": false,
          "is_pay": 0,
          "is_union_video": 0,
          "is_steins_gate": 0,
          "is_live_playback": 0,
          "meta": null,
          "is_avoided": 0,
          "attribute": 0,
          "is_charging_arc": false,
          "vt": 0,
          "enable_vt": 0,
          "vt_display": "",
          "playback_position": 0
        },
        {
          "comment": 4369,
          "typeid": 253,
          "play": 1772533,
          "pic": "http://i2.hdslb.com/bfs/archive/2986071d48373b6ee7e18543043aff6c14b9cd8e.jpg",
          "subtitle": "",
          "description": "赤犬：被偏爱的人有恃无恐\n\n图片来源说明：\n视频内容及封面使用的图片素材来自于网络搜集，素材不作为商业用途，版权归属于原创作者，仅供交流学习，部分图片来源无法考证，如有问题请务必直接与我联系！\n\n有趣的视频推荐：\n《海贼王最终秘密：乔伊·波伊完整分析》BV15i4y1277p\n《海贼王动画幕后故事》BV1iy4y1T7et\n《探秘“天王”乌拉诺斯》BV1so4y1U7CZ\n《海贼王尾田创作史》BV1tS4y1w7YY",
          "copyright": "1",
          "title": "海贼王1081话完整解说：最高战力堕落正义！铁拳卡普痛击大将！最后的路标历史正文，神秘莫测的烧伤男！",
          "review": 0,
          "author": "动漫作业本",
          "mid": 488779255,
          "created": 1681988022,
          "length": "10:45",
          "video_review": 3851,
          "aid": 397734829,
          "bvid": "BV1Ko4y1b7gC",
          "hide_click": false,
          "is_pay": 0,
          "is_union_video": 0,
          "is_steins_gate": 0,
          "is_live_playback": 0,
          "meta": {
            "id": 2658,
            "title": "【燃到冒烟】海贼王最新漫画动态解说！",
            "cover": "https://i0.hdslb.com/bfs/archive/f58dc256d3a61799af922742446593e7db1ec9e8.jpg",
            "mid": 488779255,
            "intro": "海贼王每周漫画解说，原滋原味还原每一份热血与感动！",
            "sign_state": 0,
            "attribute": 140,
            "stat": {
              "season_id": 2658,
              "view": 104526446,
              "danmaku": 292605,
              "reply": 219652,
              "favorite": 271164,
              "coin": 905601,
              "share": 201788,
              "like": 3558973,
              "mtime": 1697897788,
              "vt": 0,
              "vv": 0
            },
            "ep_count": 96,
            "first_aid": 330939965,
            "ptime": 1697084650,
            "ep_num": 96
          },
          "is_avoided": 0,
          "attribute": 0,
          "is_charging_arc": false,
          "vt": 0,
          "enable_vt": 0,
          "vt_display": "",
          "playback_position": 0
        },
        {
          "comment": 3909,
          "typeid": 253,
          "play": 1763028,
          "pic": "http://i1.hdslb.com/bfs/archive/d207ac1547ac5d7a87092828e74999e342d22bd7.jpg",
          "subtitle": "",
          "description": "“天龙人是创造了这个世界的神”\n\n图片来源说明：\n视频内容及封面使用的图片素材来自于网络搜集，素材不作为商业用途，版权归属于原创作者，仅供交流学习，部分图片来源无法考证，如有问题请务必直接与我联系！\n\n有趣的视频推荐：\n《海贼王最终秘密：乔伊·波伊完整分析》BV15i4y1277p\n《路飞五档与天落九影》BV1AF41147LA\n《海贼王动画幕后故事》BV1iy4y1T7et\n《探秘“天王”乌拉诺斯》BV1so4y1U7CZ\n《海贼王尾田创作史》BV1tS4y1w7YY",
          "copyright": "1",
          "title": "海贼王1060话完整解说：世界之王终极力量！炎帝萨博再遇劫难！路飞的终极梦想，引向最后的冒险！",
          "review": 0,
          "author": "动漫作业本",
          "mid": 488779255,
          "created": 1663322915,
          "length": "09:48",
          "video_review": 6219,
          "aid": 388121189,
          "bvid": "BV1hd4y167j5",
          "hide_click": false,
          "is_pay": 0,
          "is_union_video": 0,
          "is_steins_gate": 0,
          "is_live_playback": 0,
          "meta": {
            "id": 2658,
            "title": "【燃到冒烟】海贼王最新漫画动态解说！",
            "cover": "https://i0.hdslb.com/bfs/archive/f58dc256d3a61799af922742446593e7db1ec9e8.jpg",
            "mid": 488779255,
            "intro": "海贼王每周漫画解说，原滋原味还原每一份热血与感动！",
            "sign_state": 0,
            "attribute": 140,
            "stat": {
              "season_id": 2658,
              "view": 104526446,
              "danmaku": 292605,
              "reply": 219652,
              "favorite": 271164,
              "coin": 905601,
              "share": 201788,
              "like": 3558973,
              "mtime": 1697897788,
              "vt": 0,
              "vv": 0
            },
            "ep_count": 96,
            "first_aid": 330939965,
            "ptime": 1697084650,
            "ep_num": 96
          },
          "is_avoided": 0,
          "attribute": 0,
          "is_charging_arc": false,
          "vt": 0,
          "enable_vt": 0,
          "vt_display": "",
          "playback_position": 0
        },
        {
          "comment": 4567,
          "typeid": 253,
          "play": 1740550,
          "pic": "http://i0.hdslb.com/bfs/archive/1012a8012435b9645ed134028b34eaedcebc2572.jpg",
          "subtitle": "",
          "description": "凯多：说好的最后的四档...\n\n有趣的视频推荐：\n《海贼王最终秘密：乔伊·波伊完整分析》BV15i4y1277p\n《路飞五档与天落九影》BV1AF41147LA\n《海贼王动画幕后故事》BV1iy4y1T7et\n《探秘“天王”乌拉诺斯》BV1so4y1U7CZ\n《23年动画片头曲大合集》BV1wh411W7Mg\n《海贼王漫画结局猜想》BV1B64y1q7nL",
          "copyright": "1",
          "title": "海贼王1043话完整解说：乔伊波伊欢笑归来！自由鼓点响彻大海！绝境之中的最强觉醒！",
          "review": 0,
          "author": "动漫作业本",
          "mid": 488779255,
          "created": 1646991196,
          "length": "08:13",
          "video_review": 5514,
          "aid": 509650244,
          "bvid": "BV1hu411B76f",
          "hide_click": false,
          "is_pay": 0,
          "is_union_video": 0,
          "is_steins_gate": 0,
          "is_live_playback": 0,
          "meta": {
            "id": 2658,
            "title": "【燃到冒烟】海贼王最新漫画动态解说！",
            "cover": "https://i0.hdslb.com/bfs/archive/f58dc256d3a61799af922742446593e7db1ec9e8.jpg",
            "mid": 488779255,
            "intro": "海贼王每周漫画解说，原滋原味还原每一份热血与感动！",
            "sign_state": 0,
            "attribute": 140,
            "stat": {
              "season_id": 2658,
              "view": 104526446,
              "danmaku": 292605,
              "reply": 219652,
              "favorite": 271164,
              "coin": 905601,
              "share": 201788,
              "like": 3558973,
              "mtime": 1697897788,
              "vt": 0,
              "vv": 0
            },
            "ep_count": 96,
            "first_aid": 330939965,
            "ptime": 1697084650,
            "ep_num": 96
          },
          "is_avoided": 0,
          "attribute": 0,
          "is_charging_arc": false,
          "vt": 0,
          "enable_vt": 0,
          "vt_display": "",
          "playback_position": 0
        },
        {
          "comment": 5079,
          "typeid": 253,
          "play": 1729297,
          "pic": "http://i0.hdslb.com/bfs/archive/501d842ddba49655db6ddb277f7e66bacfc32a01.jpg",
          "subtitle": "",
          "description": "最强信号塔！\n\n图片来源说明：\n视频内容及封面使用的图片素材来自于网络搜集，素材不作为商业用途，版权归属于原创作者，仅供交流学习，部分图片来源无法考证，如有问题请务必直接与我联系！\n\n有趣的视频推荐：\n《海贼王最终秘密：乔伊·波伊完整分析》BV15i4y1277p\n《路飞五档与天落九影》BV1AF41147LA\n《海贼王动画幕后故事》BV1iy4y1T7et\n《探秘“天王”乌拉诺斯》BV1so4y1U7CZ\n《海贼王尾田创作史》BV1tS4y1w7YY",
          "copyright": "1",
          "title": "海贼王1055话完整解说：红发战意震颤大海，霸王威压喝退大将，古代兵器再次现身，800年前和之国的秘密揭开！",
          "review": 0,
          "author": "动漫作业本",
          "mid": 488779255,
          "created": 1659095440,
          "length": "08:52",
          "video_review": 7548,
          "aid": 983974977,
          "bvid": "BV1Wt4y1V7gw",
          "hide_click": false,
          "is_pay": 0,
          "is_union_video": 0,
          "is_steins_gate": 0,
          "is_live_playback": 0,
          "meta": {
            "id": 2658,
            "title": "【燃到冒烟】海贼王最新漫画动态解说！",
            "cover": "https://i0.hdslb.com/bfs/archive/f58dc256d3a61799af922742446593e7db1ec9e8.jpg",
            "mid": 488779255,
            "intro": "海贼王每周漫画解说，原滋原味还原每一份热血与感动！",
            "sign_state": 0,
            "attribute": 140,
            "stat": {
              "season_id": 2658,
              "view": 104526446,
              "danmaku": 292605,
              "reply": 219652,
              "favorite": 271164,
              "coin": 905601,
              "share": 201788,
              "like": 3558973,
              "mtime": 1697897788,
              "vt": 0,
              "vv": 0
            },
            "ep_count": 96,
            "first_aid": 330939965,
            "ptime": 1697084650,
            "ep_num": 96
          },
          "is_avoided": 0,
          "attribute": 0,
          "is_charging_arc": false,
          "vt": 0,
          "enable_vt": 0,
          "vt_display": "",
          "playback_position": 0
        },
        {
          "comment": 4915,
          "typeid": 253,
          "play": 1713634,
          "pic": "http://i0.hdslb.com/bfs/archive/d4e13ada17dc6eda0e9dc8a8946ae50017ba018a.jpg",
          "subtitle": "",
          "description": "绿牛：终于没人笑我了！\n\n图片来源说明：\n视频内容及封面使用的图片素材来自于网络搜集，素材不作为商业用途，版权归属于原创作者，仅供交流学习，部分图片来源无法考证，如有问题请务必直接与我联系！\n\n有趣的视频推荐：\n《海贼王最终秘密：乔伊·波伊完整分析》BV15i4y1277p\n《海贼王动画幕后故事》BV1iy4y1T7et\n《探秘“天王”乌拉诺斯》BV1so4y1U7CZ\n《海贼王尾田创作史》BV1tS4y1w7YY",
          "copyright": "1",
          "title": "海贼王1079话完整解说：霸王一击神魔退避！赤红霸气震颤四海！四皇红发香克斯出手，黑胡子海贼团乱入未来国？",
          "review": 0,
          "author": "动漫作业本",
          "mid": 488779255,
          "created": 1679566823,
          "length": "07:51",
          "video_review": 3460,
          "aid": 441474357,
          "bvid": "BV1EL411D7hw",
          "hide_click": false,
          "is_pay": 0,
          "is_union_video": 0,
          "is_steins_gate": 0,
          "is_live_playback": 0,
          "meta": {
            "id": 2658,
            "title": "【燃到冒烟】海贼王最新漫画动态解说！",
            "cover": "https://i0.hdslb.com/bfs/archive/f58dc256d3a61799af922742446593e7db1ec9e8.jpg",
            "mid": 488779255,
            "intro": "海贼王每周漫画解说，原滋原味还原每一份热血与感动！",
            "sign_state": 0,
            "attribute": 140,
            "stat": {
              "season_id": 2658,
              "view": 104526446,
              "danmaku": 292605,
              "reply": 219652,
              "favorite": 271164,
              "coin": 905601,
              "share": 201788,
              "like": 3558973,
              "mtime": 1697897788,
              "vt": 0,
              "vv": 0
            },
            "ep_count": 96,
            "first_aid": 330939965,
            "ptime": 1697084650,
            "ep_num": 96
          },
          "is_avoided": 0,
          "attribute": 0,
          "is_charging_arc": false,
          "vt": 0,
          "enable_vt": 0,
          "vt_display": "",
          "playback_position": 0
        },
        {
          "comment": 4283,
          "typeid": 253,
          "play": 1696341,
          "pic": "http://i0.hdslb.com/bfs/archive/724736c1ef6ef9a2bc17cec6b103dd454a353b55.jpg",
          "subtitle": "",
          "description": "赤犬：你们都别回来了！\n\n视频BGM（部分）：\n宾克斯的美酒\nwe are\n\n图片来源说明：\n视频内容及封面使用的图片素材来自于网络搜集，素材不作为商业用途，版权归属于原创作者，仅供交流学习，部分图片来源无法考证，如有问题请务必直接与我联系！\n\n有趣的视频推荐：\n《海贼王最终秘密：乔伊·波伊完整分析》BV15i4y1277p\n《路飞五档与天落九影》BV1AF41147LA\n《海贼王动画幕后故事》BV1iy4y1T7et\n《探秘“天王”乌拉诺斯》BV1so4y1U7CZ\n《海贼王尾田创作史》BV1tS4y1",
          "copyright": "1",
          "title": "海贼王1052话完整解说：大海皇帝呼之欲出！紧急事态震动圣地！和之国战斗终焉，新的危机悄然浮现，迫近的大将绿牛！",
          "review": 0,
          "author": "动漫作业本",
          "mid": 488779255,
          "created": 1654857451,
          "length": "10:13",
          "video_review": 6184,
          "aid": 639933757,
          "bvid": "BV1oY4y1W7FQ",
          "hide_click": false,
          "is_pay": 0,
          "is_union_video": 0,
          "is_steins_gate": 0,
          "is_live_playback": 0,
          "meta": {
            "id": 2658,
            "title": "【燃到冒烟】海贼王最新漫画动态解说！",
            "cover": "https://i0.hdslb.com/bfs/archive/f58dc256d3a61799af922742446593e7db1ec9e8.jpg",
            "mid": 488779255,
            "intro": "海贼王每周漫画解说，原滋原味还原每一份热血与感动！",
            "sign_state": 0,
            "attribute": 140,
            "stat": {
              "season_id": 2658,
              "view": 104526446,
              "danmaku": 292605,
              "reply": 219652,
              "favorite": 271164,
              "coin": 905601,
              "share": 201788,
              "like": 3558973,
              "mtime": 1697897788,
              "vt": 0,
              "vv": 0
            },
            "ep_count": 96,
            "first_aid": 330939965,
            "ptime": 1697084650,
            "ep_num": 96
          },
          "is_avoided": 0,
          "attribute": 0,
          "is_charging_arc": false,
          "vt": 0,
          "enable_vt": 0,
          "vt_display": "",
          "playback_position": 0
        },
        {
          "comment": 8655,
          "typeid": 253,
          "play": 1687204,
          "pic": "http://i1.hdslb.com/bfs/archive/e8fdbaadb09a2141f3aa926262660715116c9322.jpg",
          "subtitle": "",
          "description": "巴基大人，永远追随你！\n\n图片来源说明：\n视频内容及封面使用的图片素材来自于网络搜集，素材不作为商业用途，版权归属于原创作者，仅供交流学习，部分图片来源无法考证，如有问题请务必直接与我联系！\n\n有趣的视频推荐：\n《海贼王最终秘密：乔伊·波伊完整分析》BV15i4y1277p\n《路飞五档与天落九影》BV1AF41147LA\n《海贼王动画幕后故事》BV1iy4y1T7et\n《探秘“天王”乌拉诺斯》BV1so4y1U7CZ\n《海贼王尾田创作史》BV1tS4y1w7YY",
          "copyright": "1",
          "title": "海贼王1053话情报来了！最意想不到的新四皇诞生！古代兵器冥王终于现身！大将绿牛真实能力曝光！",
          "review": 0,
          "author": "动漫作业本",
          "mid": 488779255,
          "created": 1655205484,
          "length": "01:46",
          "video_review": 2584,
          "aid": 897490958,
          "bvid": "BV1PA4y1d7rR",
          "hide_click": false,
          "is_pay": 0,
          "is_union_video": 0,
          "is_steins_gate": 0,
          "is_live_playback": 0,
          "meta": {
            "id": 64412,
            "title": "【海鸥送报】海贼王每周最新情报！",
            "cover": "https://archive.biliimg.com/bfs/archive/3c25061d2cdaacac709377a18a33ba78e32d0b35.jpg",
            "mid": 488779255,
            "intro": "每周第一时间更新海贼王漫画最新情报，欢迎订阅",
            "sign_state": 0,
            "attribute": 140,
            "stat": {
              "season_id": 64412,
              "view": 109989520,
              "danmaku": 156955,
              "reply": 383762,
              "favorite": 142920,
              "coin": 362220,
              "share": 320353,
              "like": 3864880,
              "mtime": 1697897782,
              "vt": 0,
              "vv": 0
            },
            "ep_count": 166,
            "first_aid": 592592735,
            "ptime": 1697009301,
            "ep_num": 166
          },
          "is_avoided": 0,
          "attribute": 0,
          "is_charging_arc": false,
          "vt": 0,
          "enable_vt": 0,
          "vt_display": "",
          "playback_position": 0
        },
        {
          "comment": 1891,
          "typeid": 253,
          "play": 1664774,
          "pic": "http://i2.hdslb.com/bfs/archive/a8c5453e42b0b47b6cb20b254035613cedc4499d.jpg",
          "subtitle": "",
          "description": "哥斯拉！\n\n图片来源说明：\n视频内容及封面使用的图片素材来自于网络搜集，素材不作为商业用途，版权归属于原创作者，仅供交流学习，部分图片来源无法考证，如有问题请务必直接与我联系！\n\n有趣的视频推荐：\n《海贼王最终秘密：乔伊·波伊完整分析》BV15i4y1277p\n《海贼王动画幕后故事》BV1iy4y1T7et\n《探秘“天王”乌拉诺斯》BV1so4y1U7CZ\n《海贼王尾田创作史》BV1tS4y1w7YY",
          "copyright": "1",
          "title": "顶级幻兽大集结？五老星伊姆到底是什么？天龙人手中的王牌，跨越血脉的D之意志！海贼王1085话细节伏笔分析！",
          "review": 0,
          "author": "动漫作业本",
          "mid": 488779255,
          "created": 1685877074,
          "length": "10:43",
          "video_review": 3076,
          "aid": 741885568,
          "bvid": "BV1Bk4y1H77H",
          "hide_click": false,
          "is_pay": 0,
          "is_union_video": 0,
          "is_steins_gate": 0,
          "is_live_playback": 0,
          "meta": {
            "id": 74265,
            "title": "【细思极恐】海贼王细节伏笔分析！",
            "cover": "https://archive.biliimg.com/bfs/archive/c33230e2544c3e01090a2be3a2ff2d22b1d9817c.jpg",
            "mid": 488779255,
            "intro": "每周漫画剧情细节与伏笔分析！挖掘那些尾田留下的线索",
            "sign_state": 0,
            "attribute": 140,
            "stat": {
              "season_id": 74265,
              "view": 65523584,
              "danmaku": 199513,
              "reply": 143630,
              "favorite": 237371,
              "coin": 740254,
              "share": 104505,
              "like": 2716267,
              "mtime": 1697897783,
              "vt": 0,
              "vv": 0
            },
            "ep_count": 90,
            "first_aid": 850804006,
            "ptime": 1697537289,
            "ep_num": 90
          },
          "is_avoided": 0,
          "attribute": 0,
          "is_charging_arc": false,
          "vt": 0,
          "enable_vt": 0,
          "vt_display": "",
          "playback_position": 0
        },
        {
          "comment": 5840,
          "typeid": 253,
          "play": 1646861,
          "pic": "http://i2.hdslb.com/bfs/archive/f5db49effe0d42dbb1249cde74aad05a45f0313b.jpg",
          "subtitle": "",
          "description": "这不就是浪漫吗！？\n\n有趣的视频推荐：\n《海贼王动画幕后故事》BV1iy4y1T7et\n《探秘“天王”乌拉诺斯》BV1so4y1U7CZ\n《23年动画片头曲大合集》BV1wh411W7Mg\n《海贼王漫画结局猜想》BV1B64y1q7nL\n《路飞vs凯多！1036话完整解说》BV18r4y1S7GD",
          "copyright": "1",
          "title": "海贼王1043话情报来了！乔伊波伊终于诞生！跨越800年岁月，尼卡的笑声再一次响起！",
          "review": 0,
          "author": "动漫作业本",
          "mid": 488779255,
          "created": 1646753617,
          "length": "01:37",
          "video_review": 1594,
          "aid": 637031803,
          "bvid": "BV1Lb4y1W7y5",
          "hide_click": false,
          "is_pay": 0,
          "is_union_video": 0,
          "is_steins_gate": 0,
          "is_live_playback": 0,
          "meta": {
            "id": 64412,
            "title": "【海鸥送报】海贼王每周最新情报！",
            "cover": "https://archive.biliimg.com/bfs/archive/3c25061d2cdaacac709377a18a33ba78e32d0b35.jpg",
            "mid": 488779255,
            "intro": "每周第一时间更新海贼王漫画最新情报，欢迎订阅",
            "sign_state": 0,
            "attribute": 140,
            "stat": {
              "season_id": 64412,
              "view": 109989520,
              "danmaku": 156955,
              "reply": 383762,
              "favorite": 142920,
              "coin": 362220,
              "share": 320353,
              "like": 3864880,
              "mtime": 1697897782,
              "vt": 0,
              "vv": 0
            },
            "ep_count": 166,
            "first_aid": 592592735,
            "ptime": 1697009301,
            "ep_num": 166
          },
          "is_avoided": 0,
          "attribute": 0,
          "is_charging_arc": false,
          "vt": 0,
          "enable_vt": 0,
          "vt_display": "",
          "playback_position": 0
        },
        {
          "comment": 4391,
          "typeid": 253,
          "play": 1589439,
          "pic": "http://i1.hdslb.com/bfs/archive/9b548d8c5211a6939cf1c0ea6cbde33666708170.jpg",
          "subtitle": "",
          "description": "凯多：不要感冒了噢...路飞...\n\n视频BGM（部分）：\nOn Your Mark\n\n图片来源说明：\n视频内容及封面使用的图片素材来自于网络搜集，素材不作为商业用途，版权归属于原创作者，仅供交流学习，部分图片来源无法考证，如有问题请务必直接与我联系！\n\n有趣的视频推荐：\n《海贼王最终秘密：乔伊·波伊完整分析》BV15i4y1277p\n《路飞五档与天落九影》BV1AF41147LA\n《海贼王动画幕后故事》BV1iy4y1T7et\n《探秘“天王”乌拉诺斯》BV1so4y1U7CZ\n《海贼王尾田创作史》BV1",
          "copyright": "1",
          "title": "海贼王1050话完整解说：四皇败北战争结束！天落九影预言成真？寄宿着无数心愿的宝船，照亮和之国未来的世界！",
          "review": 0,
          "author": "动漫作业本",
          "mid": 488779255,
          "created": 1653646431,
          "length": "08:28",
          "video_review": 3776,
          "aid": 684430259,
          "bvid": "BV1yU4y127ip",
          "hide_click": false,
          "is_pay": 0,
          "is_union_video": 0,
          "is_steins_gate": 0,
          "is_live_playback": 0,
          "meta": {
            "id": 2658,
            "title": "【燃到冒烟】海贼王最新漫画动态解说！",
            "cover": "https://i0.hdslb.com/bfs/archive/f58dc256d3a61799af922742446593e7db1ec9e8.jpg",
            "mid": 488779255,
            "intro": "海贼王每周漫画解说，原滋原味还原每一份热血与感动！",
            "sign_state": 0,
            "attribute": 140,
            "stat": {
              "season_id": 2658,
              "view": 104526446,
              "danmaku": 292605,
              "reply": 219652,
              "favorite": 271164,
              "coin": 905601,
              "share": 201788,
              "like": 3558973,
              "mtime": 1697897788,
              "vt": 0,
              "vv": 0
            },
            "ep_count": 96,
            "first_aid": 330939965,
            "ptime": 1697084650,
            "ep_num": 96
          },
          "is_avoided": 0,
          "attribute": 0,
          "is_charging_arc": false,
          "vt": 0,
          "enable_vt": 0,
          "vt_display": "",
          "playback_position": 0
        },
        {
          "comment": 2936,
          "typeid": 253,
          "play": 1579072,
          "pic": "http://i1.hdslb.com/bfs/archive/4b87d0f731d87b1091b3b12873412217985ec81c.jpg",
          "subtitle": "",
          "description": "凯多：这一次，我不会逃！\n\n\n图片来源说明：\n视频内容及封面使用的图片素材来自于网络搜集，素材不作为商业用途，版权归属于原创作者，仅供交流学习，部分图片来源无法考证，如有问题请务必直接与我联系！\n\n有趣的视频推荐：\n《海贼王最终秘密：乔伊·波伊完整分析》BV15i4y1277p\n《路飞五档与天落九影》BV1AF41147LA\n《海贼王动画幕后故事》BV1iy4y1T7et\n《探秘“天王”乌拉诺斯》BV1so4y1U7CZ\n《23年动画片头曲大合集》BV1wh411W7Mg\n《",
          "copyright": "1",
          "title": "海贼王1048话完整解说：烈焰火龙焚尽一切！猿王神枪破开拂晓！和之国最后的回忆杀，了断黑炭光月宿命的一剑！",
          "review": 0,
          "author": "动漫作业本",
          "mid": 488779255,
          "created": 1651839703,
          "length": "08:35",
          "video_review": 4467,
          "aid": 896263130,
          "bvid": "BV17A4y1Q7r2",
          "hide_click": false,
          "is_pay": 0,
          "is_union_video": 0,
          "is_steins_gate": 0,
          "is_live_playback": 0,
          "meta": {
            "id": 2658,
            "title": "【燃到冒烟】海贼王最新漫画动态解说！",
            "cover": "https://i0.hdslb.com/bfs/archive/f58dc256d3a61799af922742446593e7db1ec9e8.jpg",
            "mid": 488779255,
            "intro": "海贼王每周漫画解说，原滋原味还原每一份热血与感动！",
            "sign_state": 0,
            "attribute": 140,
            "stat": {
              "season_id": 2658,
              "view": 104526446,
              "danmaku": 292605,
              "reply": 219652,
              "favorite": 271164,
              "coin": 905601,
              "share": 201788,
              "like": 3558973,
              "mtime": 1697897788,
              "vt": 0,
              "vv": 0
            },
            "ep_count": 96,
            "first_aid": 330939965,
            "ptime": 1697084650,
            "ep_num": 96
          },
          "is_avoided": 0,
          "attribute": 0,
          "is_charging_arc": false,
          "vt": 0,
          "enable_vt": 0,
          "vt_display": "",
          "playback_position": 0
        },
        {
          "comment": 3456,
          "typeid": 253,
          "play": 1559375,
          "pic": "http://i2.hdslb.com/bfs/archive/787250c36bfb41c0d3797bc014e0f22c8bb5d356.jpg",
          "subtitle": "",
          "description": "虚假的乔伊波伊：挨揍下海变搞笑男\n真正的乔伊波伊：吃香喝辣公会无敌\n\n图片来源说明：\n视频内容及封面使用的图片素材来自于网络搜集，素材不作为商业用途，版权归属于原创作者，仅供交流学习，部分图片来源无法考证，如有问题请务必直接与我联系！\n\n有趣的视频推荐：\n《海贼王最终秘密：乔伊·波伊完整分析》BV15i4y1277p\n《路飞五档与天落九影》BV1AF41147LA\n《海贼王动画幕后故事》BV1iy4y1T7et\n《探秘“天王”乌拉诺斯》BV1so4y1U7CZ\n《海贼王尾田创作史》BV1tS4y1w7YY",
          "copyright": "1",
          "title": "海贼王1056话完整解说：新的航线正式开启！邪恶强敌十字公会！大和到底会不会上船，和之国篇进入最后倒计时！",
          "review": 0,
          "author": "动漫作业本",
          "mid": 488779255,
          "created": 1659694436,
          "length": "09:09",
          "video_review": 6762,
          "aid": 216657258,
          "bvid": "BV19a411N7sf",
          "hide_click": false,
          "is_pay": 0,
          "is_union_video": 0,
          "is_steins_gate": 0,
          "is_live_playback": 0,
          "meta": {
            "id": 2658,
            "title": "【燃到冒烟】海贼王最新漫画动态解说！",
            "cover": "https://i0.hdslb.com/bfs/archive/f58dc256d3a61799af922742446593e7db1ec9e8.jpg",
            "mid": 488779255,
            "intro": "海贼王每周漫画解说，原滋原味还原每一份热血与感动！",
            "sign_state": 0,
            "attribute": 140,
            "stat": {
              "season_id": 2658,
              "view": 104526446,
              "danmaku": 292605,
              "reply": 219652,
              "favorite": 271164,
              "coin": 905601,
              "share": 201788,
              "like": 3558973,
              "mtime": 1697897788,
              "vt": 0,
              "vv": 0
            },
            "ep_count": 96,
            "first_aid": 330939965,
            "ptime": 1697084650,
            "ep_num": 96
          },
          "is_avoided": 0,
          "attribute": 0,
          "is_charging_arc": false,
          "vt": 0,
          "enable_vt": 0,
          "vt_display": "",
          "playback_position": 0
        }
      ],
      "slist": []
    },
    "page": {
      "pn": 1,
      "ps": 30,
      "count": 655
    },
    "episodic_button": {
      "text": "播放全部",
      "uri": "//www.bilibili.com/medialist/play/488779255?from=space"
    },
    "is_risk": false,
    "gaia_res_type": 0,
    "gaia_data": null
  }
}
```

### 返回结果

|状态码|状态码含义|说明|数据模型|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|成功|Inline|

### 返回数据结构

状态码 **200**

|名称|类型|必选|约束|中文名|说明|
|---|---|---|---|---|---|
|» code|integer|true|none||none|
|» message|string|true|none||none|
|» ttl|integer|true|none||none|
|» data|object|true|none||none|
|»» list|object|false|none|列表|none|
|»»» tlist|object|true|none|类型列表|none|
|»»»» 1|object|true|none||none|
|»»»»» tid|integer|true|none|类型id|none|
|»»»»» count|integer|true|none|类型下的视频数量|none|
|»»»»» name|string|true|none|类型名称|none|
|»»»» 4|object|true|none||none|
|»»»»» tid|integer|true|none||none|
|»»»»» count|integer|true|none||none|
|»»»»» name|string|true|none||none|
|»»»» 160|object|true|none||none|
|»»»»» tid|integer|true|none||none|
|»»»»» count|integer|true|none||none|
|»»»»» name|string|true|none||none|
|»»»» 181|object|true|none||none|
|»»»»» tid|integer|true|none||none|
|»»»»» count|integer|true|none||none|
|»»»»» name|string|true|none||none|
|»»» vlist|[object]|true|none|视频列表|none|
|»»»» comment|integer|true|none|评论数|none|
|»»»» typeid|integer|true|none|类型Id|none|
|»»»» play|integer|true|none|播放书|none|
|»»»» pic|string|true|none|封面图|none|
|»»»» subtitle|string|true|none|子标题|none|
|»»»» description|string|true|none|简介|none|
|»»»» copyright|string|true|none|是否自制|none|
|»»»» title|string|true|none|标题|none|
|»»»» review|integer|true|none||none|
|»»»» author|string|true|none||none|
|»»»» mid|integer|true|none|用户id|none|
|»»»» created|integer|true|none|创建时间|时间戳|
|»»»» length|string|true|none|时长|例如1:24|
|»»»» video_review|integer|true|none||none|
|»»»» aid|integer|true|none|作品id|none|
|»»»» bvid|string|true|none|bv号|none|
|»»»» hide_click|boolean|true|none||none|
|»»»» is_pay|integer|true|none||none|
|»»»» is_union_video|integer|true|none||none|
|»»»» is_steins_gate|integer|true|none||none|
|»»»» is_live_playback|integer|true|none|是否为直播回放|none|
|»»»» meta|object|true|none|合集信息|none|
|»»»»» id|integer|true|none||none|
|»»»»» title|string|true|none|合集标题|none|
|»»»»» cover|string|true|none|封面图|none|
|»»»»» mid|integer|true|none|用户id|none|
|»»»»» intro|string|true|none|合集简介|none|
|»»»»» sign_state|integer|true|none||none|
|»»»»» attribute|integer|true|none||none|
|»»»»» stat|object|true|none||none|
|»»»»»» season_id|integer|true|none|合集id|none|
|»»»»»» view|integer|true|none|总播放量|none|
|»»»»»» danmaku|integer|true|none|总弹幕数|none|
|»»»»»» reply|integer|true|none|总评论数|none|
|»»»»»» favorite|integer|true|none|总收藏数|none|
|»»»»»» coin|integer|true|none|总投币数|none|
|»»»»»» share|integer|true|none|总分享数|none|
|»»»»»» like|integer|true|none|总点赞数|none|
|»»»»»» mtime|integer|true|none||none|
|»»»»»» vt|integer|true|none||none|
|»»»»»» vv|integer|true|none||none|
|»»»»» ep_count|integer|true|none|视频数量|none|
|»»»»» first_aid|integer|true|none|第一个视频id|none|
|»»»»» ptime|integer|true|none|最新更新时间|none|
|»»»»» ep_num|integer|true|none|视频数量|none|
|»»»» is_avoided|integer|true|none||none|
|»»»» attribute|integer|true|none||none|
|»»»» is_charging_arc|boolean|true|none||none|
|»»»» vt|integer|true|none||none|
|»»»» enable_vt|integer|true|none||none|
|»»»» vt_display|string|true|none||none|
|»»»» playback_position|integer|true|none||none|
|»»» slist|[string]|true|none||none|
|»» page|object|false|none||none|
|»»» pn|integer|true|none|页码|none|
|»»» ps|integer|true|none|每页大小|none|
|»»» count|integer|true|none|总数量|none|
|»» episodic_button|object|false|none||none|
|»»» text|string|true|none||none|
|»»» uri|string|true|none||none|
|»» is_risk|boolean|false|none||none|
|»» gaia_res_type|integer|false|none||none|
|»» gaia_data|null|false|none||none|

## GET 音频列表

GET /audio/music-service/web/song/upper

### 请求参数

|名称|位置|类型|必选|说明|
|---|---|---|---|---|
|uid|query|string| 否 |用户id|
|pn|query|string| 否 |页码|
|ps|query|string| 否 |每页数量|
|order|query|string| 否 |1最新发布，2最多播放, 3最多收藏|
|User-Agent|header|string| 否 |none|

> 返回示例

> 成功

```json
{
  "code": 0,
  "msg": "success",
  "data": {
    "curPage": 1,
    "pageCount": 1,
    "totalSize": 0,
    "pageSize": 30,
    "data": null
  }
}
```

### 返回结果

|状态码|状态码含义|说明|数据模型|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|成功|Inline|

### 返回数据结构

## GET 文章列表

GET /x/space/wbi/article

### 请求参数

|名称|位置|类型|必选|说明|
|---|---|---|---|---|
|mid|query|string| 否 |用户id|
|pn|query|string| 否 |页码|
|ps|query|string| 否 |每页数量|
|sort|query|string| 否 |排序方式 publish_time, view, fav|
|User-Agent|header|string| 否 |none|

> 返回示例

> 200 Response

```json
{}
```

### 返回结果

|状态码|状态码含义|说明|数据模型|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|成功|Inline|

### 返回数据结构

## GET 相薄列表

GET /x/dynamic/feed/draw/doc_list

### 请求参数

|名称|位置|类型|必选|说明|
|---|---|---|---|---|
|uid|query|string| 否 |none|
|page_num|query|string| 否 |页码, 从0开始|
|page_size|query|string| 否 |每页数量|
|biz|query|string| 否 |all, daily|
|User-Agent|header|string| 否 |none|

> 返回示例

> 成功

```json
{
  "code": 0,
  "message": "0",
  "ttl": 1,
  "data": {
    "items": [
      {
        "doc_id": 284892281,
        "poster_uid": 488779255,
        "title": "",
        "description": "玲玲酱当时说的“缺失的三个种族”，现在应该清楚了吧[doge]1.巨人族 2.露娜里亚族 3.巴卡尼亚族！",
        "pictures": [
          {
            "img_src": "https://i0.hdslb.com/bfs/new_dyn/247a984447367cd25f67610723348068488779255.png",
            "img_width": 762,
            "img_height": 428,
            "img_size": 235.85546875,
            "img_tags": null
          }
        ],
        "count": 1,
        "ctime": 1697682868,
        "view": 453553,
        "like": 3018,
        "dyn_id": "854030487055761445"
      },
      {
        "doc_id": 284746866,
        "poster_uid": 488779255,
        "title": "",
        "description": "熊找到了尼卡[委屈]（来自画师ripped1taliano）",
        "pictures": [
          {
            "img_src": "https://i0.hdslb.com/bfs/new_dyn/2943054d2ec299fbd1c52a388aac7a7e488779255.jpg",
            "img_width": 3000,
            "img_height": 4000,
            "img_size": 1777.0927734375,
            "img_tags": null
          }
        ],
        "count": 1,
        "ctime": 1697618729,
        "view": 381342,
        "like": 3322,
        "dyn_id": "853755012177723426"
      },
      {
        "doc_id": 284390649,
        "poster_uid": 488779255,
        "title": "",
        "description": "海军的戏份不多，但其实中将里面都有绝活（从左往右）——\n1.名字未知，疑似动物系海獭果实能力者\n2.道伯曼中将，剑士\n3.朵尔中将，疑似足长族\n4.名字未知，狙击手\n5.名字未知，脑袋可以变成一门大炮\n6.布鲁格拉斯中将，骑骑果实能力者\n7.名字未知\n8.名字未知，右手是强大的机械臂\n9.名字未知，脑袋可以变出刀刃",
        "pictures": [
          {
            "img_src": "https://i0.hdslb.com/bfs/new_dyn/0e519d5c6b77e1028ef14dfcc176f86d488779255.png",
            "img_width": 1130,
            "img_height": 1074,
            "img_size": 1095.8916015625,
            "img_tags": null
          },
          {
            "img_src": "https://i0.hdslb.com/bfs/new_dyn/0ae3ed9633c9fe9ca56925292bf60bbc488779255.png",
            "img_width": 456,
            "img_height": 568,
            "img_size": 288.544921875,
            "img_tags": null
          },
          {
            "img_src": "https://i0.hdslb.com/bfs/new_dyn/4a2c8834a91531e97d041e6024c80f8b488779255.png",
            "img_width": 896,
            "img_height": 602,
            "img_size": 605.2216796875,
            "img_tags": null
          },
          {
            "img_src": "https://i0.hdslb.com/bfs/new_dyn/31dbe21d406227a547ce25f1b5dc4f9c488779255.png",
            "img_width": 1140,
            "img_height": 356,
            "img_size": 398.732421875,
            "img_tags": null
          },
          {
            "img_src": "https://i0.hdslb.com/bfs/new_dyn/f8a715eb51879f7ba613d0288da6d0ed488779255.png",
            "img_width": 782,
            "img_height": 488,
            "img_size": 309.140625,
            "img_tags": null
          }
        ],
        "count": 5,
        "ctime": 1697462193,
        "view": 544768,
        "like": 1780,
        "dyn_id": "853082695177076758"
      },
      {
        "doc_id": 284280438,
        "poster_uid": 488779255,
        "title": "",
        "description": "小时候熊期待尼卡来拯救自己，长大后却在不经意间救了尼卡...得救之道，从来都是在自己手中啊！尾田太会了",
        "pictures": [
          {
            "img_src": "https://i0.hdslb.com/bfs/new_dyn/6d8854f6b84089b806d1a9f9cb41c20e488779255.png",
            "img_width": 1096,
            "img_height": 526,
            "img_size": 565.8427734375,
            "img_tags": null
          },
          {
            "img_src": "https://i0.hdslb.com/bfs/new_dyn/9a0e97e171ab32ed3b83cc31d9cfe8d0488779255.png",
            "img_width": 1060,
            "img_height": 410,
            "img_size": 339.755859375,
            "img_tags": null
          },
          {
            "img_src": "https://i0.hdslb.com/bfs/new_dyn/7b171c6750446eefc530c6bdb9a1da00488779255.png",
            "img_width": 1056,
            "img_height": 480,
            "img_size": 415.96484375,
            "img_tags": null
          }
        ],
        "count": 3,
        "ctime": 1697427722,
        "view": 430135,
        "like": 3128,
        "dyn_id": "852934643354173445"
      },
      {
        "doc_id": 284059500,
        "poster_uid": 488779255,
        "title": "",
        "description": "哆啦A梦？ ❌\n大将绿牛！✅\n\n接下来的故事属实让人难绷[妙啊]",
        "pictures": [
          {
            "img_src": "https://i0.hdslb.com/bfs/new_dyn/39b6c054e26b7582efe7e7c69dc1893d488779255.gif",
            "img_width": 474,
            "img_height": 266,
            "img_size": 4600.6416015625,
            "img_tags": null
          },
          {
            "img_src": "https://i0.hdslb.com/bfs/new_dyn/018780d8befa41b7aecd49b7c2b65665488779255.gif",
            "img_width": 474,
            "img_height": 266,
            "img_size": 6902.939453125,
            "img_tags": null
          }
        ],
        "count": 2,
        "ctime": 1697345685,
        "view": 440882,
        "like": 2209,
        "dyn_id": "852582297360138312"
      },
      {
        "doc_id": 284053630,
        "poster_uid": 488779255,
        "title": "",
        "description": "给娜美CPU干烧了，大和（女）要去男澡堂，小菊（男）要去女澡堂[抠鼻]",
        "pictures": [
          {
            "img_src": "https://i0.hdslb.com/bfs/new_dyn/95e03a1e4a41c639f93a1c16e7d9a421488779255.gif",
            "img_width": 474,
            "img_height": 266,
            "img_size": 1108.4970703125,
            "img_tags": null
          }
        ],
        "count": 1,
        "ctime": 1697344454,
        "view": 374529,
        "like": 2337,
        "dyn_id": "852577010004787209"
      },
      {
        "doc_id": 283815771,
        "poster_uid": 488779255,
        "title": "",
        "description": "高清图源终于能看清了，这6个箱子就是天龙人给所谓的“比赛”准备好的奖励吧[脱单doge]里面有凯多那颗青龙果实吗？明哥果然是天龙人出来的小鬼，斗牛竞技场学得有模有样～",
        "pictures": [
          {
            "img_src": "https://i0.hdslb.com/bfs/new_dyn/005249033f029d0d0914b3fb959bde69488779255.png",
            "img_width": 2078,
            "img_height": 1028,
            "img_size": 1538.2197265625,
            "img_tags": null
          },
          {
            "img_src": "https://i0.hdslb.com/bfs/new_dyn/f5bd5e0e3cc0eaedd1dbb7bea46a7676488779255.png",
            "img_width": 440,
            "img_height": 388,
            "img_size": 145.841796875,
            "img_tags": null
          }
        ],
        "count": 2,
        "ctime": 1697264700,
        "view": 413910,
        "like": 2393,
        "dyn_id": "852234469433671682"
      },
      {
        "doc_id": 283774582,
        "poster_uid": 488779255,
        "title": "",
        "description": "给加林圣换上香克斯的脸，是不是更有那味了[妙啊]",
        "pictures": [
          {
            "img_src": "https://i0.hdslb.com/bfs/new_dyn/4857f1440157396bf05b6ec2c8d2ada2488779255.jpg",
            "img_width": 853,
            "img_height": 2048,
            "img_size": 335.9638671875,
            "img_tags": null
          },
          {
            "img_src": "https://i0.hdslb.com/bfs/new_dyn/85c43d8d21b34e2e31c3496258f17473488779255.jpg",
            "img_width": 1296,
            "img_height": 1248,
            "img_size": 257.5869140625,
            "img_tags": null
          }
        ],
        "count": 2,
        "ctime": 1697253572,
        "view": 415795,
        "like": 2204,
        "dyn_id": "852186674790137880"
      },
      {
        "doc_id": 283711591,
        "poster_uid": 488779255,
        "title": "",
        "description": "大熊这个哭泣，应该会成为海贼王中经典镜头吧..他明明什么都没做错，却失去了一切...[大哭]",
        "pictures": [
          {
            "img_src": "https://i0.hdslb.com/bfs/new_dyn/4304d05d257d5a35b1d9c5dd9ce16576488779255.jpg",
            "img_width": 508,
            "img_height": 507,
            "img_size": 69.720703125,
            "img_tags": null
          }
        ],
        "count": 1,
        "ctime": 1697213042,
        "view": 515444,
        "like": 4084,
        "dyn_id": "852012599763533924"
      },
      {
        "doc_id": 283563553,
        "poster_uid": 488779255,
        "title": "",
        "description": "上一话光顾着看萨坦变身，其实路飞这一下还是挺猛的，直接把黄猿打到起不来了... 武装色+霸王色缠绕+五档腕力+橡胶同化+音爆+“星星”+火焰，这应该是目前效果最多的一招吧...待遇超越凯老师那次。",
        "pictures": [
          {
            "img_src": "https://i0.hdslb.com/bfs/new_dyn/41abc063a88c599ffe89b61da30c10f0488779255.jpg",
            "img_width": 3009,
            "img_height": 3059,
            "img_size": 971.5302734375,
            "img_tags": null
          },
          {
            "img_src": "https://i0.hdslb.com/bfs/new_dyn/db4da3865a60f4758210309aa3e6686c488779255.png",
            "img_width": 1130,
            "img_height": 1068,
            "img_size": 1098.306640625,
            "img_tags": null
          },
          {
            "img_src": "https://i0.hdslb.com/bfs/new_dyn/b3a7a933b48352f27b4964a458e6f311488779255.png",
            "img_width": 1146,
            "img_height": 502,
            "img_size": 579.4423828125,
            "img_tags": null
          },
          {
            "img_src": "https://i0.hdslb.com/bfs/new_dyn/981ef2b3757526a000662c4faf6e3851488779255.png",
            "img_width": 1076,
            "img_height": 820,
            "img_size": 981.630859375,
            "img_tags": null
          }
        ],
        "count": 4,
        "ctime": 1697170697,
        "view": 485796,
        "like": 2244,
        "dyn_id": "851830729373384743"
      },
      {
        "doc_id": 283484822,
        "poster_uid": 488779255,
        "title": "",
        "description": "正写着神之谷，越看越觉得洛克斯这标志...好像很眼熟啊！和尼卡一样的“弯曲头发”，脸上的裂痕也跟路飞一样，最骚的是路飞当时在长环岛比赛时，胸前画了个标志，又很像洛克斯的旗帜...[妙啊]尾田到底想干嘛",
        "pictures": [
          {
            "img_src": "https://i0.hdslb.com/bfs/new_dyn/f5867327f2710d2368c468eefabb008a488779255.png",
            "img_width": 278,
            "img_height": 196,
            "img_size": 59.498046875,
            "img_tags": null
          },
          {
            "img_src": "https://i0.hdslb.com/bfs/new_dyn/fe7780782c2d17ee83b31c670749e85c488779255.png",
            "img_width": 88,
            "img_height": 120,
            "img_size": 15.146484375,
            "img_tags": null
          },
          {
            "img_src": "https://i0.hdslb.com/bfs/new_dyn/e876c7c2816e69db0eb4ba8d135d691e488779255.png",
            "img_width": 1082,
            "img_height": 860,
            "img_size": 713.9228515625,
            "img_tags": null
          },
          {
            "img_src": "https://i0.hdslb.com/bfs/new_dyn/d5a7ab4680f0d1b12198af55768d26c5488779255.png",
            "img_width": 180,
            "img_height": 244,
            "img_size": 43.693359375,
            "img_tags": null
          },
          {
            "img_src": "https://i0.hdslb.com/bfs/new_dyn/0a0480284cbeccde7e319888c8974fcc488779255.png",
            "img_width": 680,
            "img_height": 476,
            "img_size": 294.849609375,
            "img_tags": null
          },
          {
            "img_src": "https://i0.hdslb.com/bfs/new_dyn/0becdc40550ca172e37a4f3e93d4ebe9488779255.png",
            "img_width": 500,
            "img_height": 438,
            "img_size": 185.7392578125,
            "img_tags": null
          }
        ],
        "count": 6,
        "ctime": 1697122440,
        "view": 548764,
        "like": 2083,
        "dyn_id": "851623467135533156"
      },
      {
        "doc_id": 283271902,
        "poster_uid": 488779255,
        "title": "",
        "description": "虽然大家猜测金妮是老沙小时候，不过老沙小时候的样子并不是这样...两人性格也很不一样，一个i人一个e人，应该不会同一个[妙啊]",
        "pictures": [
          {
            "img_src": "https://i0.hdslb.com/bfs/new_dyn/e0f8541451de7fe56b5251f728570bba488779255.png",
            "img_width": 518,
            "img_height": 804,
            "img_size": 579.98828125,
            "img_tags": null
          },
          {
            "img_src": "https://i0.hdslb.com/bfs/new_dyn/41a8fb3d324e626e9028f0869f182b59488779255.png",
            "img_width": 300,
            "img_height": 600,
            "img_size": 124.5107421875,
            "img_tags": null
          }
        ],
        "count": 2,
        "ctime": 1697033870,
        "view": 505757,
        "like": 1816,
        "dyn_id": "851243061869543489"
      },
      {
        "doc_id": 283237006,
        "poster_uid": 488779255,
        "title": "",
        "description": "发型对男人来说真的很重要啊！[妙啊]",
        "pictures": [
          {
            "img_src": "https://i0.hdslb.com/bfs/new_dyn/0908393cf466870526a9c0ffd930ebe6488779255.jpg",
            "img_width": 1027,
            "img_height": 2048,
            "img_size": 311.83984375,
            "img_tags": null
          },
          {
            "img_src": "https://i0.hdslb.com/bfs/new_dyn/c664d8ea8425e9939586353c124b37c2488779255.jpg",
            "img_width": 1427,
            "img_height": 2048,
            "img_size": 363.0234375,
            "img_tags": null
          },
          {
            "img_src": "https://i0.hdslb.com/bfs/new_dyn/e9f725bdbacd24af09ed3e1df487ba68488779255.png",
            "img_width": 652,
            "img_height": 752,
            "img_size": 811.904296875,
            "img_tags": null
          },
          {
            "img_src": "https://i0.hdslb.com/bfs/new_dyn/ee3efc647182f42889262fc4e69081be488779255.png",
            "img_width": 316,
            "img_height": 462,
            "img_size": 152.197265625,
            "img_tags": null
          }
        ],
        "count": 4,
        "ctime": 1697023669,
        "view": 403585,
        "like": 2014,
        "dyn_id": "851199248923885590"
      },
      {
        "doc_id": 283109613,
        "poster_uid": 488779255,
        "title": "",
        "description": "1095话情报补充...天龙人每三年举行一次竞赛，这是一种“狩猎比赛”。他们选择一个不隶属于世界政府的岛屿作为举办比赛的地方，比如“神之谷”，他们将“无用又麻烦的奴隶”聚齐起来，然后开始猎杀...[惊讶]",
        "pictures": [
          {
            "img_src": "https://i0.hdslb.com/bfs/new_dyn/7d51f1bd60f4cce53a9568769180589d488779255.jpg",
            "img_width": 1280,
            "img_height": 720,
            "img_size": 690.9599609375,
            "img_tags": null
          }
        ],
        "count": 1,
        "ctime": 1696959470,
        "view": 448363,
        "like": 1616,
        "dyn_id": "850923512009850933"
      },
      {
        "doc_id": 283053186,
        "poster_uid": 488779255,
        "title": "",
        "description": "如果不是因为神之谷事件，香克斯本来应该是...[妙啊]",
        "pictures": [
          {
            "img_src": "https://i0.hdslb.com/bfs/new_dyn/5168d622f77524e310ea51f290cb44f5488779255.png",
            "img_width": 701,
            "img_height": 553,
            "img_size": 793.9814453125,
            "img_tags": null
          }
        ],
        "count": 1,
        "ctime": 1696942610,
        "view": 566473,
        "like": 4409,
        "dyn_id": "850851103172984870"
      },
      {
        "doc_id": 283026557,
        "poster_uid": 488779255,
        "title": "",
        "description": "1095话情报新补充：本话将会有一个新的妹子角色！[妙啊]",
        "pictures": [
          {
            "img_src": "https://i0.hdslb.com/bfs/new_dyn/55bcbf5feaa0177a25d18d6c3f93201a488779255.jpg",
            "img_width": 3036,
            "img_height": 2248,
            "img_size": 11307.720703125,
            "img_tags": null
          }
        ],
        "count": 1,
        "ctime": 1696935164,
        "view": 367776,
        "like": 2702,
        "dyn_id": "850819122843353108"
      },
      {
        "doc_id": 282985838,
        "poster_uid": 488779255,
        "title": "",
        "description": "神之谷如果确认在“西海”，那么洛克斯海贼团从新世界去西海，肯定穿越了无风带...以这个团的狠人来说，应该没啥难度...",
        "pictures": [
          {
            "img_src": "https://i0.hdslb.com/bfs/new_dyn/3622e120e967ab9e1c07518b1b0bcec0488779255.png",
            "img_width": 1120,
            "img_height": 554,
            "img_size": 614.3388671875,
            "img_tags": null
          },
          {
            "img_src": "https://i0.hdslb.com/bfs/new_dyn/d43c55d0252bacac43d18caea517eee2488779255.jpg",
            "img_width": 1200,
            "img_height": 900,
            "img_size": 162.2158203125,
            "img_tags": null
          }
        ],
        "count": 2,
        "ctime": 1696921465,
        "view": 367157,
        "like": 2095,
        "dyn_id": "850760286090559494"
      },
      {
        "doc_id": 282948706,
        "poster_uid": 488779255,
        "title": "",
        "description": "白胡子：​“每次看到你的脸，那小子在我身上留下的伤口就隐隐作痛...”[doge]所以白胡子说的是真的是加林？",
        "pictures": [
          {
            "img_src": "https://i0.hdslb.com/bfs/new_dyn/42c04e0ffc67f48e2a2cea738d727447488779255.png",
            "img_width": 2252,
            "img_height": 1682,
            "img_size": 2864.3798828125,
            "img_tags": null
          }
        ],
        "count": 1,
        "ctime": 1696907524,
        "view": 413969,
        "like": 2394,
        "dyn_id": "850700409946243097"
      },
      {
        "doc_id": 282928877,
        "poster_uid": 488779255,
        "title": "",
        "description": "海贼王1095话第1波情报，作业本翻译，来自英文情报[脱单doge]\n-我们将会看到大熊的回忆，并知晓他的父亲如何在神之谷中死亡\n-天龙人在神之谷中组织了一场比武大会，让不同种族的人互相厮杀\n-我们可以看到年轻时的费加兰德·加林，他看起来和香克斯一模一样，只是发型不同\n-大熊的种族将会揭秘！",
        "pictures": [
          {
            "img_src": "https://i0.hdslb.com/bfs/new_dyn/dcd106c41f82123f2d4e3bff14715858488779255.jpg",
            "img_width": 628,
            "img_height": 621,
            "img_size": 77.21875,
            "img_tags": null
          }
        ],
        "count": 1,
        "ctime": 1696897538,
        "view": 407067,
        "like": 1662,
        "dyn_id": "850657520390242312"
      },
      {
        "doc_id": 282806465,
        "poster_uid": 488779255,
        "title": "",
        "description": "1095话情报新提示...一个球？[doge]",
        "pictures": [
          {
            "img_src": "https://i0.hdslb.com/bfs/new_dyn/50a47e9dcf6abbc298088ba19de36804488779255.gif",
            "img_width": 400,
            "img_height": 300,
            "img_size": 113.560546875,
            "img_tags": null
          }
        ],
        "count": 1,
        "ctime": 1696840694,
        "view": 324879,
        "like": 1394,
        "dyn_id": "850413377267171347"
      },
      {
        "doc_id": 282734272,
        "poster_uid": 488779255,
        "title": "",
        "description": "1095话首条确认情报：本话将会有神之谷与费加兰德·加林圣的剧情！[大笑]",
        "pictures": [
          {
            "img_src": "https://i0.hdslb.com/bfs/new_dyn/a1e2fae249ef0c7b6ea6ceae1fcff2ce488779255.jpg",
            "img_width": 4096,
            "img_height": 2560,
            "img_size": 498.2216796875,
            "img_tags": null
          }
        ],
        "count": 1,
        "ctime": 1696809364,
        "view": 398636,
        "like": 2210,
        "dyn_id": "850278815966953479"
      },
      {
        "doc_id": 282733732,
        "poster_uid": 488779255,
        "title": "",
        "description": "1095话首个情报提示，来自redon[doge]看起来真的有什么催泪剧情？...",
        "pictures": [
          {
            "img_src": "https://i0.hdslb.com/bfs/new_dyn/6b79b5e3f5915016854eddedd4b175ff488779255.gif",
            "img_width": 220,
            "img_height": 124,
            "img_size": 736.2138671875,
            "img_tags": null
          }
        ],
        "count": 1,
        "ctime": 1696809071,
        "view": 298278,
        "like": 1185,
        "dyn_id": "850277557779562504"
      },
      {
        "doc_id": 282696847,
        "poster_uid": 488779255,
        "title": "",
        "description": "路飞：太有趣啦，萨坦！[妙啊]",
        "pictures": [
          {
            "img_src": "https://i0.hdslb.com/bfs/new_dyn/3ca66beee87ea7b33a0e63d8e3543348488779255.jpg",
            "img_width": 2124,
            "img_height": 1500,
            "img_size": 450.0517578125,
            "img_tags": null
          }
        ],
        "count": 1,
        "ctime": 1696778664,
        "view": 424974,
        "like": 2201,
        "dyn_id": "850146960458383408"
      },
      {
        "doc_id": 282660070,
        "poster_uid": 488779255,
        "title": "",
        "description": "这就开始了，情报师剧透1095话是“高潮”和“悲伤”并存的一话...[妙啊]配图C罗拿奖，有那味了...",
        "pictures": [
          {
            "img_src": "https://i0.hdslb.com/bfs/new_dyn/38f04a2d11732fb03ced6f5d089c2dbb488779255.png",
            "img_width": 1180,
            "img_height": 874,
            "img_size": 728.634765625,
            "img_tags": null
          }
        ],
        "count": 1,
        "ctime": 1696769642,
        "view": 381507,
        "like": 2037,
        "dyn_id": "850108211276021766"
      },
      {
        "doc_id": 282610491,
        "poster_uid": 488779255,
        "title": "",
        "description": "在古代，海贼入秋换衣服啦[脱单doge]​\n神级羊毛啊！！贝落客旗舰店！！\n三合一加绒冲锋衣！！男女同款！59元起！！\n\n一衣三穿，反馈好评无数\n专业户外御寒装备，不挑年龄身材，暴雨级防水超级牛！！！\n外层高密度面料，严密防风、防水，大风大雨都不带怕！！\n内层透气网布拼接设计，轻薄+保暖+透气❗\n---------------\n长按复制这条信息，打开手机淘宝下单：4$ZvEpW0r6uCt$:// ZH9114\n",
        "pictures": [
          {
            "img_src": "https://i0.hdslb.com/bfs/new_dyn/945f678033072d3e4584776a5f75496f488779255.jpg",
            "img_width": 800,
            "img_height": 698,
            "img_size": 104.6259765625,
            "img_tags": null
          },
          {
            "img_src": "https://i0.hdslb.com/bfs/new_dyn/951638a94af33d0d6d19bddc79f7778b488779255.jpg",
            "img_width": 1290,
            "img_height": 1555,
            "img_size": 281.1474609375,
            "img_tags": null
          },
          {
            "img_src": "https://i0.hdslb.com/bfs/new_dyn/9a8766f6e1d6accbec29d5aecc66a09a488779255.jpg",
            "img_width": 923,
            "img_height": 1337,
            "img_size": 88.20703125,
            "img_tags": null
          },
          {
            "img_src": "https://i0.hdslb.com/bfs/new_dyn/118119dad089bfa92c849f9e7d4633d9488779255.jpg",
            "img_width": 600,
            "img_height": 600,
            "img_size": 65.0107421875,
            "img_tags": null
          },
          {
            "img_src": "https://i0.hdslb.com/bfs/new_dyn/d38e367e073c71c2d4cc55bfea34f14f488779255.jpg",
            "img_width": 1080,
            "img_height": 1440,
            "img_size": 185.5712890625,
            "img_tags": null
          },
          {
            "img_src": "https://i0.hdslb.com/bfs/new_dyn/2528f85f3700a53904cd3bfb140defa3488779255.png",
            "img_width": 800,
            "img_height": 800,
            "img_size": 495.435546875,
            "img_tags": null
          }
        ],
        "count": 6,
        "ctime": 1696755839,
        "view": 303819,
        "like": 624,
        "dyn_id": "850048932114333704"
      },
      {
        "doc_id": 282549772,
        "poster_uid": 488779255,
        "title": "",
        "description": "大将绿牛的新声优确认为诹访部顺一！ 之前曾经是海贼王“鬼竹”维尔戈的声优，也配过不少经典动漫角色...另外他还是宿傩的声优[妙啊]",
        "pictures": [
          {
            "img_src": "https://i0.hdslb.com/bfs/new_dyn/0da0522769ca2165c3f29cbea19a6420488779255.png",
            "img_width": 556,
            "img_height": 680,
            "img_size": 828.724609375,
            "img_tags": null
          }
        ],
        "count": 1,
        "ctime": 1696732741,
        "view": 362111,
        "like": 2456,
        "dyn_id": "849949722663714820"
      },
      {
        "doc_id": 282465377,
        "poster_uid": 488779255,
        "title": "",
        "description": "1095话首条确认的情报[doge]下周不休刊！五老星持续加班～",
        "pictures": [
          {
            "img_src": "https://i0.hdslb.com/bfs/new_dyn/31222d0414d54a3f89edb861d8ec0546488779255.jpg",
            "img_width": 1779,
            "img_height": 2048,
            "img_size": 797.47265625,
            "img_tags": null
          }
        ],
        "count": 1,
        "ctime": 1696684902,
        "view": 463179,
        "like": 2748,
        "dyn_id": "849744255752601652"
      },
      {
        "doc_id": 282448640,
        "poster_uid": 488779255,
        "title": "",
        "description": "《萨坦圣地工作日常流出》[妙啊]",
        "pictures": [
          {
            "img_src": "https://i0.hdslb.com/bfs/new_dyn/08ebc79c68502a0cec5d694d609bf145488779255.gif",
            "img_width": 498,
            "img_height": 274,
            "img_size": 747.205078125,
            "img_tags": null
          }
        ],
        "count": 1,
        "ctime": 1696680495,
        "view": 370211,
        "like": 2320,
        "dyn_id": "849725327828582437"
      },
      {
        "doc_id": 282188292,
        "poster_uid": 488779255,
        "title": "",
        "description": "黑影之一归位！！[妙啊] 萨坦的牛角、蜘蛛腿，甚至拄着拐杖的手肘，都能对上...尾田看来已经把形象想好了",
        "pictures": [
          {
            "img_src": "https://i0.hdslb.com/bfs/new_dyn/5d0b7a814d07bb87f5613471f0e5a03d488779255.png",
            "img_width": 1280,
            "img_height": 922,
            "img_size": 945.986328125,
            "img_tags": null
          },
          {
            "img_src": "https://i0.hdslb.com/bfs/new_dyn/c2b0f49c97895a04e2e77c578507ea80488779255.png",
            "img_width": 1262,
            "img_height": 908,
            "img_size": 1590.01953125,
            "img_tags": null
          }
        ],
        "count": 2,
        "ctime": 1696580080,
        "view": 457006,
        "like": 2924,
        "dyn_id": "849294048676020226"
      },
      {
        "doc_id": 282113662,
        "poster_uid": 488779255,
        "title": "",
        "description": "[doge]接下来值得期待的几集动画：\n1080集，公布新四皇，预计10月22日播出\n1082集，红发霸王色霸气，绿牛冥场面，预计11月5日播出\n1085集，剧情正式进入未来岛篇！",
        "pictures": [
          {
            "img_src": "https://i0.hdslb.com/bfs/new_dyn/9a7db4cd40dc2eb2593d9972fe1bf150488779255.jpg",
            "img_width": 695,
            "img_height": 1080,
            "img_size": 252.634765625,
            "img_tags": null
          }
        ],
        "count": 1,
        "ctime": 1696561754,
        "view": 430914,
        "like": 1876,
        "dyn_id": "849215339089625096"
      }
    ]
  }
}
```

### 返回结果

|状态码|状态码含义|说明|数据模型|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|成功|Inline|

### 返回数据结构

状态码 **200**

|名称|类型|必选|约束|中文名|说明|
|---|---|---|---|---|---|
|» code|integer|true|none||none|
|» message|string|true|none||none|
|» ttl|integer|true|none||none|
|» data|object|true|none||none|
|»» items|[object]|true|none||none|
|»»» doc_id|integer|true|none||none|
|»»» poster_uid|integer|true|none||none|
|»»» title|string|true|none||none|
|»»» description|string|true|none||none|
|»»» pictures|[object]|true|none||none|
|»»»» img_src|string|true|none||none|
|»»»» img_width|integer|true|none||none|
|»»»» img_height|integer|true|none||none|
|»»»» img_size|number|true|none||none|
|»»»» img_tags|null|true|none||none|
|»»» count|integer|true|none||none|
|»»» ctime|integer|true|none||none|
|»»» view|integer|true|none||none|
|»»» like|integer|true|none||none|
|»»» dyn_id|string|true|none||none|

## GET 相簿数量

GET /x/dynamic/feed/draw/upload_count

### 请求参数

|名称|位置|类型|必选|说明|
|---|---|---|---|---|
|uid|query|string| 否 |用户id|
|User-Agent|header|string| 否 |none|

> 返回示例

> 成功

```json
{
  "code": 0,
  "message": "0",
  "ttl": 1,
  "data": {
    "all_count": 1458,
    "draw_count": 0,
    "photo_count": 0,
    "daily_count": 1458
  }
}
```

### 返回结果

|状态码|状态码含义|说明|数据模型|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|成功|Inline|

### 返回数据结构

状态码 **200**

|名称|类型|必选|约束|中文名|说明|
|---|---|---|---|---|---|
|» code|integer|true|none||none|
|» message|string|true|none||none|
|» ttl|integer|true|none||none|
|» data|object|true|none||none|
|»» all_count|integer|true|none||none|
|»» draw_count|integer|true|none||none|
|»» photo_count|integer|true|none||none|
|»» daily_count|integer|true|none||none|

## GET 合集列表

GET /x/polymer/web-space/seasons_series_list

### 请求参数

|名称|位置|类型|必选|说明|
|---|---|---|---|---|
|mid|query|string| 否 |none|
|page_num|query|string| 否 |none|
|page_size|query|string| 否 |none|
|User-Agent|header|string| 否 |none|

> 返回示例

> 成功

```json
{
  "code": 0,
  "message": "0",
  "ttl": 1,
  "data": {
    "items_lists": {
      "page": {
        "page_num": 1,
        "page_size": 20,
        "total": 12
      },
      "seasons_list": [
        {
          "archives": [
            {
              "aid": 769237776,
              "bvid": "BV1ar4y1473c",
              "ctime": 1652953565,
              "duration": 536,
              "enable_vt": false,
              "interactive_video": false,
              "pic": "http://i1.hdslb.com/bfs/archive/11a499e91520a3741c247ddac95bd2bc1c422940.jpg",
              "playback_position": 0,
              "pubdate": 1652953565,
              "stat": {
                "view": 900089,
                "vt": 0
              },
              "state": 0,
              "title": "路飞的终极梦想是什么？揭开海贼王结局伏笔之一！吃饱饭的世界有什么深意？完整盘点两代海贼王的共同目标！",
              "ugc_pay": 0,
              "vt_display": ""
            },
            {
              "aid": 811675316,
              "bvid": "BV1u34y1E7gT",
              "ctime": 1653044617,
              "duration": 375,
              "enable_vt": false,
              "interactive_video": false,
              "pic": "http://i1.hdslb.com/bfs/archive/c9d4a0384e01f0e2eea4c51e898271fc155cc1cb.jpg",
              "playback_position": 0,
              "pubdate": 1653044616,
              "stat": {
                "view": 453456,
                "vt": 0
              },
              "state": 0,
              "title": "海贼王中有爱情故事吗？盘点海贼5大刻骨铭心的爱恋！另类的眼泪与感动，520特别纪念篇！",
              "ugc_pay": 0,
              "vt_display": ""
            },
            {
              "aid": 214639636,
              "bvid": "BV15a41177te",
              "ctime": 1654401902,
              "duration": 326,
              "enable_vt": false,
              "interactive_video": false,
              "pic": "http://i2.hdslb.com/bfs/archive/2c722ab97b6e3af88c2bd5f60405d2730b6ee03f.jpg",
              "playback_position": 0,
              "pubdate": 1654401899,
              "stat": {
                "view": 994237,
                "vt": 0
              },
              "state": 0,
              "title": "盘点海贼王最神秘的8个人！大结局前尚未揭晓的伏笔，草帽一伙的最终BOSS，海贼王最终章看点集合！",
              "ugc_pay": 0,
              "vt_display": ""
            },
            {
              "aid": 897895876,
              "bvid": "BV1UN4y1u7Yy",
              "ctime": 1656417144,
              "duration": 837,
              "enable_vt": false,
              "interactive_video": false,
              "pic": "http://i0.hdslb.com/bfs/archive/989ed841f4a03c410644190ab12a322bbbcb9dee.jpg",
              "playback_position": 0,
              "pubdate": 1656417144,
              "stat": {
                "view": 1166484,
                "vt": 0
              },
              "state": 0,
              "title": "一口气看完海贼王所有名刀！4把无上大快刀，5把大快刀，最强黑刀与霸气之间有何关联？",
              "ugc_pay": 0,
              "vt_display": ""
            },
            {
              "aid": 897958671,
              "bvid": "BV1gN4y1g7uv",
              "ctime": 1656582774,
              "duration": 336,
              "enable_vt": false,
              "interactive_video": false,
              "pic": "http://i0.hdslb.com/bfs/archive/cf03a8ed2c6c01a042e4695074a79136e6cb59f5.jpg",
              "playback_position": 0,
              "pubdate": 1656582774,
              "stat": {
                "view": 818037,
                "vt": 0
              },
              "state": 0,
              "title": "一口气看完目前海军主力！ 海军干部与12生肖对应？盘点海军本部大将与大将候补",
              "ugc_pay": 0,
              "vt_display": ""
            },
            {
              "aid": 770434775,
              "bvid": "BV1fr4y1g7Cn",
              "ctime": 1656661299,
              "duration": 440,
              "enable_vt": false,
              "interactive_video": false,
              "pic": "http://i1.hdslb.com/bfs/archive/d00e46347861b758a61ebe5d1454d1aa198c1695.jpg",
              "playback_position": 0,
              "pubdate": 1656661299,
              "stat": {
                "view": 407647,
                "vt": 0
              },
              "state": 0,
              "title": "赤鞘九侠原本是7个？尾田草稿设定大公开！《Road To Laugh Tale》第1期完整解读，路飞还有更帅的造型！",
              "ugc_pay": 0,
              "vt_display": ""
            }
          ],
          "meta": {
            "category": 0,
            "cover": "https://archive.biliimg.com/bfs/archive/58575d184c1a996d1ab0a4a54b48af0577479e21.jpg",
            "description": "独特的漫画分析系列，每期针对一个细分主题，讲好故事",
            "mid": 488779255,
            "name": "合集·【海式漫谈】讲好每一个漫画细节",
            "ptime": 1697797549,
            "season_id": 426614,
            "total": 58
          },
          "recent_aids": [
            769237776,
            811675316,
            214639636,
            897895876,
            897958671,
            770434775
          ]
        },
        {
          "archives": [
            {
              "aid": 850804006,
              "bvid": "BV1FL4y1t7BJ",
              "ctime": 1642765233,
              "duration": 390,
              "enable_vt": false,
              "interactive_video": false,
              "pic": "http://i1.hdslb.com/bfs/archive/2787e5253073bd3bf483dc8606fcc31a285efa0c.jpg",
              "playback_position": 0,
              "pubdate": 1642765233,
              "stat": {
                "view": 924493,
                "vt": 0
              },
              "state": 0,
              "title": "盘点索隆所有7把佩刀！从和道一文字到地狱之王，黑刀练就之路，登顶剑豪通途！",
              "ugc_pay": 0,
              "vt_display": ""
            },
            {
              "aid": 808301465,
              "bvid": "BV1S34y1i7MC",
              "ctime": 1642591721,
              "duration": 589,
              "enable_vt": false,
              "interactive_video": false,
              "pic": "http://i1.hdslb.com/bfs/archive/d80a6705bbba22ca9a0acbabfa0c653ad6c50015.jpg",
              "playback_position": 0,
              "pubdate": 1642591721,
              "stat": {
                "view": 434009,
                "vt": 0
              },
              "state": 0,
              "title": "倾听万物之声的秘密！象主因何行动？潜藏在那个人身上的天王之力，终于苏醒！海贼王1037话细节分析下篇",
              "ugc_pay": 0,
              "vt_display": ""
            },
            {
              "aid": 508144621,
              "bvid": "BV1Ru41127aq",
              "ctime": 1642418100,
              "duration": 578,
              "enable_vt": false,
              "interactive_video": false,
              "pic": "http://i1.hdslb.com/bfs/archive/6e395186575a257dbc72f7b351d5a4eed6000bcb.jpg",
              "playback_position": 0,
              "pubdate": 1642418100,
              "stat": {
                "view": 511031,
                "vt": 0
              },
              "state": 0,
              "title": "海贼王1037话分析上篇：红心的诅咒？天龙人掌控的终极奥秘，能够夺取世界实权的恶魔果实之力！",
              "ugc_pay": 0,
              "vt_display": ""
            },
            {
              "aid": 850379561,
              "bvid": "BV1EL4y1J7DM",
              "ctime": 1641209632,
              "duration": 433,
              "enable_vt": false,
              "interactive_video": false,
              "pic": "http://i1.hdslb.com/bfs/archive/036f35d3189b89b50f0fd6f5026a980db2107775.jpg",
              "playback_position": 0,
              "pubdate": 1641209631,
              "stat": {
                "view": 443437,
                "vt": 0
              },
              "state": 0,
              "title": "和之国伏笔大盘点！D之一族与乔伊波伊的关系，太阳神尼卡的传说意味着什么？海贼王1036话细节伏笔分析上篇",
              "ugc_pay": 0,
              "vt_display": ""
            },
            {
              "aid": 680407562,
              "bvid": "BV1xS4y1T7zf",
              "ctime": 1641378016,
              "duration": 594,
              "enable_vt": false,
              "interactive_video": false,
              "pic": "http://i2.hdslb.com/bfs/archive/7108fb72fb970fbf549d8dcb090b8731b54e43c1.jpg",
              "playback_position": 0,
              "pubdate": 1641378013,
              "stat": {
                "view": 449610,
                "vt": 0
              },
              "state": 0,
              "title": "即将到来的最终章会是什么？席卷世界的巨大战争马上开始，古代兵器终于重现人间，海贼王1036话细节伏笔分析下篇",
              "ugc_pay": 0,
              "vt_display": ""
            },
            {
              "aid": 635074995,
              "bvid": "BV1Cb4y1v7Vh",
              "ctime": 1640232302,
              "duration": 400,
              "enable_vt": false,
              "interactive_video": false,
              "pic": "http://i2.hdslb.com/bfs/archive/367e912857dfc0aac38b30e206eb7d4de1f9340c.jpg",
              "playback_position": 0,
              "pubdate": 1640232301,
              "stat": {
                "view": 665367,
                "vt": 0
              },
              "state": 0,
              "title": "结合了鬼气与霸王色的索隆，即将晋级为“地狱之王”？海贼王1035话细节分析下篇，聊聊鬼岛决战的结局",
              "ugc_pay": 0,
              "vt_display": ""
            }
          ],
          "meta": {
            "category": 0,
            "cover": "https://archive.biliimg.com/bfs/archive/c33230e2544c3e01090a2be3a2ff2d22b1d9817c.jpg",
            "description": "每周漫画剧情细节与伏笔分析！挖掘那些尾田留下的线索",
            "mid": 488779255,
            "name": "合集·【细思极恐】海贼王细节伏笔分析！",
            "ptime": 1697537289,
            "season_id": 74265,
            "total": 90
          },
          "recent_aids": [
            850804006,
            808301465,
            508144621,
            850379561,
            680407562,
            635074995
          ]
        },
        {
          "archives": [
            {
              "aid": 823119711,
              "bvid": "BV1Ng4y1J7UQ",
              "ctime": 1678005943,
              "duration": 386,
              "enable_vt": false,
              "interactive_video": false,
              "pic": "http://i2.hdslb.com/bfs/archive/ed8c7b52e79860799822f1a091b66e5f5dd8730d.jpg",
              "playback_position": 0,
              "pubdate": 1678005943,
              "stat": {
                "view": 589409,
                "vt": 0
              },
              "state": 0,
              "title": "最强控制果实居然有“两颗”！动物系可以修炼改变型态？甜甜果实与猫猫果实，官方恶魔果实图鉴更新！",
              "ugc_pay": 0,
              "vt_display": ""
            },
            {
              "aid": 681506574,
              "bvid": "BV19S4y1G7c3",
              "ctime": 1645094117,
              "duration": 340,
              "enable_vt": false,
              "interactive_video": false,
              "pic": "http://i1.hdslb.com/bfs/archive/c234aec136fac9e5096a2d8dac9f593e678937bb.jpg",
              "playback_position": 0,
              "pubdate": 1645094116,
              "stat": {
                "view": 675298,
                "vt": 0
              },
              "state": 0,
              "title": "天花板无限高的恶魔果实？空间果实已经出现过了？盘点海贼王中，那些想象力巨大的恶魔果实",
              "ugc_pay": 0,
              "vt_display": ""
            },
            {
              "aid": 423437741,
              "bvid": "BV1h3411h7x9",
              "ctime": 1643020227,
              "duration": 222,
              "enable_vt": false,
              "interactive_video": false,
              "pic": "http://i1.hdslb.com/bfs/archive/83e1ecd8f69c5a1cc5229eac51d2df9f7c2bb261.jpg",
              "playback_position": 0,
              "pubdate": 1643020226,
              "stat": {
                "view": 1553652,
                "vt": 0
              },
              "state": 0,
              "title": "吃了又好像没吃！能够切换型态的蛋！盘点那些奇奇怪怪的恶魔果实能力，乔巴风评被害！",
              "ugc_pay": 0,
              "vt_display": ""
            },
            {
              "aid": 722155673,
              "bvid": "BV1NS4y197RG",
              "ctime": 1639130314,
              "duration": 250,
              "enable_vt": false,
              "interactive_video": false,
              "pic": "http://i0.hdslb.com/bfs/archive/8f54e2bfec75d68ae1e8d60395b7223688887a64.jpg",
              "playback_position": 0,
              "pubdate": 1639130314,
              "stat": {
                "view": 307279,
                "vt": 0
              },
              "state": 0,
              "title": "盘点和之国篇4大幻兽种恶魔果实！人人果实自带说话功能，鱼鱼果实暗合神话！海贼王恶魔果实图鉴",
              "ugc_pay": 0,
              "vt_display": ""
            },
            {
              "aid": 546442087,
              "bvid": "BV1Qq4y1s7kg",
              "ctime": 1625034814,
              "duration": 487,
              "enable_vt": false,
              "interactive_video": false,
              "pic": "http://i0.hdslb.com/bfs/archive/0fd2a7b6ef84cea6fb9a3cdc64a8234f35630e65.jpg",
              "playback_position": 0,
              "pubdate": 1625048401,
              "stat": {
                "view": 714294,
                "vt": 0
              },
              "state": 0,
              "title": "年 糕 达 人 ！最 强 将 星！恶魔果实图鉴之超人系糯糯果实！夏洛特家族最高杰作，卡塔库栗的招式完整盘点",
              "ugc_pay": 0,
              "vt_display": ""
            },
            {
              "aid": 82962444,
              "bvid": "BV1AJ411p7Zt",
              "ctime": 1578725977,
              "duration": 176,
              "enable_vt": false,
              "interactive_video": false,
              "pic": "http://i1.hdslb.com/bfs/archive/41ef5f43c696a52910928df03c646357b260f674.jpg",
              "playback_position": 0,
              "pubdate": 1578725977,
              "stat": {
                "view": 171411,
                "vt": 0
              },
              "state": 0,
              "title": "《恶魔果实图鉴》最特殊的自然系！史上最凶恶的恶魔果实能力！",
              "ugc_pay": 0,
              "vt_display": ""
            }
          ],
          "meta": {
            "category": 0,
            "cover": "https://archive.biliimg.com/bfs/archive/8072933e8446c4fed8cfd50c40055b9518098904.jpg",
            "description": "",
            "mid": 488779255,
            "name": "合集·【脑洞大开】海贼王恶魔果实图鉴",
            "ptime": 1697363970,
            "season_id": 202553,
            "total": 23
          },
          "recent_aids": [
            823119711,
            681506574,
            423437741,
            722155673,
            546442087,
            82962444
          ]
        },
        {
          "archives": [
            {
              "aid": 330939965,
              "bvid": "BV1KA411W72n",
              "ctime": 1609426911,
              "duration": 541,
              "enable_vt": false,
              "interactive_video": false,
              "pic": "http://i0.hdslb.com/bfs/archive/7b7c84ba8ea1c3cdff9b59bddad924915fc6ada7.jpg",
              "playback_position": 0,
              "pubdate": 1609426910,
              "stat": {
                "view": 1508075,
                "vt": 0
              },
              "state": 0,
              "title": "海贼王漫画解说1000话《草帽路飞》：揭开世界的黎明，我是蒙奇·D·路飞，将会成为海贼王的男人！",
              "ugc_pay": 0,
              "vt_display": ""
            },
            {
              "aid": 331138091,
              "bvid": "BV17A411H7EF",
              "ctime": 1611035737,
              "duration": 436,
              "enable_vt": false,
              "interactive_video": false,
              "pic": "http://i2.hdslb.com/bfs/archive/4748ca31c8f9341f3c3163f62903361677e173ea.jpg",
              "playback_position": 0,
              "pubdate": 1611035736,
              "stat": {
                "view": 489699,
                "vt": 0
              },
              "state": 0,
              "title": "海贼王漫画解说1001话《鬼之岛怪物决战》：赢下这场战争的人，就离海贼王的宝座不远了！来吧，怪物们！",
              "ugc_pay": 0,
              "vt_display": ""
            },
            {
              "aid": 501493828,
              "bvid": "BV1PN411R7L7",
              "ctime": 1612097053,
              "duration": 421,
              "enable_vt": false,
              "interactive_video": false,
              "pic": "http://i0.hdslb.com/bfs/archive/a23610fbaba54a269f499d2ca8f48f4df46e6482.jpg",
              "playback_position": 0,
              "pubdate": 1612097053,
              "stat": {
                "view": 431238,
                "vt": 0
              },
              "state": 0,
              "title": "海贼王漫画解说1002话《四皇VS新世代》：旧时代的铜墙铁壁，就由我来彻底打碎！",
              "ugc_pay": 0,
              "vt_display": ""
            },
            {
              "aid": 246547909,
              "bvid": "BV1zv411e7Kv",
              "ctime": 1612793118,
              "duration": 645,
              "enable_vt": false,
              "interactive_video": false,
              "pic": "http://i0.hdslb.com/bfs/archive/29de45f9fc5f1efa565e2e8abd85a42aa77e7e50.jpg",
              "playback_position": 0,
              "pubdate": 1612793118,
              "stat": {
                "view": 427608,
                "vt": 0
              },
              "state": 0,
              "title": "海贼王漫画解说1003话《盘上之夜》：阎魔神锋再次斩龙！凯多爆气第三型态！意想不到的势力入局了...",
              "ugc_pay": 0,
              "vt_display": ""
            },
            {
              "aid": 459210822,
              "bvid": "BV1p5411E7HJ",
              "ctime": 1613475016,
              "duration": 500,
              "enable_vt": false,
              "interactive_video": false,
              "pic": "http://i1.hdslb.com/bfs/archive/4d5dd05e0ff12fdc3a39ded7a726cfe1464b4bd3.jpg",
              "playback_position": 0,
              "pubdate": 1613475016,
              "stat": {
                "view": 333900,
                "vt": 0
              },
              "state": 0,
              "title": "海贼王漫画解说1004话《糯米团子》：神奇宝贝大师就是我！阿玉！百兽海贼团终极克星登场，神秘人物救援赤鞘九侠",
              "ugc_pay": 0,
              "vt_display": ""
            },
            {
              "aid": 586902305,
              "bvid": "BV1Gz4y1m75m",
              "ctime": 1614520718,
              "duration": 542,
              "enable_vt": false,
              "interactive_video": false,
              "pic": "http://i1.hdslb.com/bfs/archive/e37e0fb7466b54b17e0e262364263dfe3deb15b2.jpg",
              "playback_position": 0,
              "pubdate": 1614520718,
              "stat": {
                "view": 360326,
                "vt": 0
              },
              "state": 0,
              "title": "海贼王漫画解说1005话《恶魔之子》：花在任何地方都会绽放！你可别小瞧了，妮可·罗宾啊！",
              "ugc_pay": 0,
              "vt_display": ""
            }
          ],
          "meta": {
            "category": 0,
            "cover": "https://i0.hdslb.com/bfs/archive/f58dc256d3a61799af922742446593e7db1ec9e8.jpg",
            "description": "海贼王每周漫画解说，原滋原味还原每一份热血与感动！",
            "mid": 488779255,
            "name": "合集·【燃到冒烟】海贼王最新漫画动态解说！",
            "ptime": 1697084650,
            "season_id": 2658,
            "total": 96
          },
          "recent_aids": [
            330939965,
            331138091,
            501493828,
            246547909,
            459210822,
            586902305
          ]
        },
        {
          "archives": [
            {
              "aid": 592592735,
              "bvid": "BV1sq4y1m7QF",
              "ctime": 1640348803,
              "duration": 203,
              "enable_vt": false,
              "interactive_video": false,
              "pic": "http://i0.hdslb.com/bfs/archive/b7011742949067f3176db8dc84d8d3bb7a8f5e20.jpg",
              "playback_position": 0,
              "pubdate": 1640348803,
              "stat": {
                "view": 1911776,
                "vt": 0
              },
              "state": 0,
              "title": "海贼王1036话全图情报：凯多也是乔伊波伊？索隆加冕地狱之王，鬼岛战线超级大回顾！",
              "ugc_pay": 0,
              "vt_display": ""
            },
            {
              "aid": 807573913,
              "bvid": "BV1M34y1r7G4",
              "ctime": 1640170064,
              "duration": 87,
              "enable_vt": false,
              "interactive_video": false,
              "pic": "http://i2.hdslb.com/bfs/archive/76184c889e555f14a91ccacbffde030ac0051b72.jpg",
              "playback_position": 0,
              "pubdate": 1640170064,
              "stat": {
                "view": 552460,
                "vt": 0
              },
              "state": 0,
              "title": "海贼王1036话情报来了！CP0击败德雷克，大和抵达火药库！路飞凯多巅峰对决，势均力敌？",
              "ugc_pay": 0,
              "vt_display": ""
            },
            {
              "aid": 849925065,
              "bvid": "BV16L4y1J7tS",
              "ctime": 1639643927,
              "duration": 171,
              "enable_vt": false,
              "interactive_video": false,
              "pic": "http://i1.hdslb.com/bfs/archive/14515e65a794677e78dafadd61df55c2fcd20dde.jpg",
              "playback_position": 0,
              "pubdate": 1639643927,
              "stat": {
                "view": 323721,
                "vt": 0
              },
              "state": 0,
              "title": "海贼王1035话全图情报：索隆新大招斩落火龙！山治一脚绝杀奎因！凯多与烬回忆杀出现！",
              "ugc_pay": 0,
              "vt_display": ""
            },
            {
              "aid": 892354655,
              "bvid": "BV1BP4y1n7LC",
              "ctime": 1639485527,
              "duration": 115,
              "enable_vt": false,
              "interactive_video": false,
              "pic": "http://i1.hdslb.com/bfs/archive/2e6121313a3a439c7a4e9f578e869baaeaf07c7b.jpg",
              "playback_position": 0,
              "pubdate": 1639485527,
              "stat": {
                "view": 502112,
                "vt": 0
              },
              "state": 0,
              "title": "海贼王1035话情报来了！烬真面目曝光！奎因彻底败北！索隆展现霸王色霸气新大招！",
              "ugc_pay": 0,
              "vt_display": ""
            },
            {
              "aid": 719621232,
              "bvid": "BV1LQ4y1e79a",
              "ctime": 1638432079,
              "duration": 168,
              "enable_vt": false,
              "interactive_video": false,
              "pic": "http://i0.hdslb.com/bfs/archive/41d8c1d099979de392251204e18d2c115614f54b.jpg",
              "playback_position": 0,
              "pubdate": 1638432078,
              "stat": {
                "view": 254107,
                "vt": 0
              },
              "state": 0,
              "title": "海贼王1034话全图情报！山治猛招大爆发，恶魔风脚也开始漏电了！奎因一人集齐杰尔马黑科技！",
              "ugc_pay": 0,
              "vt_display": ""
            },
            {
              "aid": 892107046,
              "bvid": "BV1jP4y137dk",
              "ctime": 1638277121,
              "duration": 91,
              "enable_vt": false,
              "interactive_video": false,
              "pic": "http://i0.hdslb.com/bfs/archive/58e623d1d5cdf6504b130a20943e5c2503df9aa4.jpg",
              "playback_position": 0,
              "pubdate": 1638277121,
              "stat": {
                "view": 353927,
                "vt": 0
              },
              "state": 0,
              "title": "海贼王1034话情报来了！恶魔风脚力量进阶，山治冤情得到洗白！奎因具备杰尔马科技之力！",
              "ugc_pay": 0,
              "vt_display": ""
            }
          ],
          "meta": {
            "category": 0,
            "cover": "https://archive.biliimg.com/bfs/archive/3c25061d2cdaacac709377a18a33ba78e32d0b35.jpg",
            "description": "每周第一时间更新海贼王漫画最新情报，欢迎订阅",
            "mid": 488779255,
            "name": "合集·【海鸥送报】海贼王每周最新情报！",
            "ptime": 1697009301,
            "season_id": 64412,
            "total": 166
          },
          "recent_aids": [
            592592735,
            807573913,
            849925065,
            892354655,
            719621232,
            892107046
          ]
        },
        {
          "archives": [
            {
              "aid": 616244250,
              "bvid": "BV1Qh4y1L7EV",
              "ctime": 1690006066,
              "duration": 295,
              "enable_vt": false,
              "interactive_video": false,
              "pic": "http://i0.hdslb.com/bfs/archive/fcf774d030f1285ac63730d0b87c0818f833575a.jpg",
              "playback_position": 0,
              "pubdate": 1690006066,
              "stat": {
                "view": 1214724,
                "vt": 0
              },
              "state": 0,
              "title": "路飞五档上线官宣预告！尼卡型态即将在8月6日到来！最乱来的能力，还是3个隐藏潜力？",
              "ugc_pay": 0,
              "vt_display": ""
            },
            {
              "aid": 359018170,
              "bvid": "BV1UX4y1E7JW",
              "ctime": 1690698286,
              "duration": 167,
              "enable_vt": false,
              "interactive_video": false,
              "pic": "http://i1.hdslb.com/bfs/archive/2348ec10ff2effea372571fd271856088c375d11.jpg",
              "playback_position": 0,
              "pubdate": 1690698286,
              "stat": {
                "view": 852161,
                "vt": 0
              },
              "state": 0,
              "title": "解放之鼓正式上线！五档路飞觉醒前夕！鼓点是否符合你的想象？海贼王动画1070集更新！",
              "ugc_pay": 0,
              "vt_display": ""
            },
            {
              "aid": 999363070,
              "bvid": "BV1B44y1w7XJ",
              "ctime": 1691153617,
              "duration": 281,
              "enable_vt": false,
              "interactive_video": false,
              "pic": "http://i0.hdslb.com/bfs/archive/3262b6be2c20601993dd9b401a8bf4dbaa4b26e8.jpg",
              "playback_position": 0,
              "pubdate": 1691153617,
              "stat": {
                "view": 511420,
                "vt": 0
              },
              "state": 0,
              "title": "五档路飞的三大特性！尼卡型态即将点燃夏天！尾田草稿设定细节回顾！",
              "ugc_pay": 0,
              "vt_display": ""
            },
            {
              "aid": 786954328,
              "bvid": "BV1E14y1z777",
              "ctime": 1691295317,
              "duration": 281,
              "enable_vt": false,
              "interactive_video": false,
              "pic": "http://i0.hdslb.com/bfs/archive/301eb100d5522ea61887f8824ad03b1c114fceab.jpg",
              "playback_position": 0,
              "pubdate": 1691295317,
              "stat": {
                "view": 1401373,
                "vt": 0
              },
              "state": 0,
              "title": "五档路飞巅峰上线！尼卡型态闪耀大海！海贼王1071集超超超高燃作画！被五档点燃的夏天终于到了！",
              "ugc_pay": 0,
              "vt_display": ""
            },
            {
              "aid": 956877084,
              "bvid": "BV1Jp4y137Ca",
              "ctime": 1691401520,
              "duration": 439,
              "enable_vt": false,
              "interactive_video": false,
              "pic": "http://i2.hdslb.com/bfs/archive/866605ff36dea025e86a71f167bfd9728a8cb0ff.jpg",
              "playback_position": 0,
              "pubdate": 1691401520,
              "stat": {
                "view": 1413125,
                "vt": 0
              },
              "state": 0,
              "title": "一口气看完路飞所有7个型态！从2档蒸汽到5档太阳神！梦魇和尼卡哪个是你的菜？五档路飞见证觉醒之路！",
              "ugc_pay": 0,
              "vt_display": ""
            },
            {
              "aid": 489734002,
              "bvid": "BV14N411z7Ty",
              "ctime": 1691913329,
              "duration": 376,
              "enable_vt": false,
              "interactive_video": false,
              "pic": "http://i0.hdslb.com/bfs/archive/f7f666c03f455f39a139b90fd1c1ebdfafa3ff52.jpg",
              "playback_position": 0,
              "pubdate": 1691913329,
              "stat": {
                "view": 885103,
                "vt": 0
              },
              "state": 0,
              "title": "能超越五档的还是五档？海贼王1072集超高燃作画！五档路飞暴打凯多！二度启动再战魔龙！",
              "ugc_pay": 0,
              "vt_display": ""
            }
          ],
          "meta": {
            "category": 0,
            "cover": "https://archive.biliimg.com/bfs/archive/c7daf0355d31de2a3e163c1f6495e7b3187edff0.jpg",
            "description": "",
            "mid": 488779255,
            "name": "合集·【五档高燃】五档路飞觉醒！燃爆整个夏天！",
            "ptime": 1694934630,
            "season_id": 1578242,
            "total": 9
          },
          "recent_aids": [
            616244250,
            359018170,
            999363070,
            786954328,
            956877084,
            489734002
          ]
        }
      ],
      "series_list": [
        {
          "archives": [
            {
              "aid": 967933230,
              "bvid": "BV1Qp4y1X7qV",
              "ctime": 1587986822,
              "duration": 576,
              "enable_vt": false,
              "interactive_video": false,
              "pic": "http://i0.hdslb.com/bfs/archive/333cf335b8c9f7d7930c404b70df8d89428dbb17.jpg",
              "playback_position": 0,
              "pubdate": 1587986822,
              "stat": {
                "view": 113050,
                "vt": 0
              },
              "state": 0,
              "title": "恶魔果实图鉴：萌即是正义！盘点海贼王中4.5个萝莉所拥有的恐怖力量！",
              "ugc_pay": 0,
              "vt_display": ""
            },
            {
              "aid": 925166199,
              "bvid": "BV1NT4y1G7dG",
              "ctime": 1586290688,
              "duration": 368,
              "enable_vt": false,
              "interactive_video": false,
              "pic": "http://i1.hdslb.com/bfs/archive/eb1cca028b0f62fbcab1bfc79dab31772415c7db.jpg",
              "playback_position": 0,
              "pubdate": 1586397168,
              "stat": {
                "view": 130115,
                "vt": 0
              },
              "state": 0,
              "title": "恶魔果实图鉴：无穷能量碾压对手！综合实力超强的自然系果实！",
              "ugc_pay": 0,
              "vt_display": ""
            },
            {
              "aid": 98900944,
              "bvid": "BV1L741127MT",
              "ctime": 1585061170,
              "duration": 301,
              "enable_vt": false,
              "interactive_video": false,
              "pic": "http://i0.hdslb.com/bfs/archive/18a6dba4ec31a1ebd05842e69e171f7f0297b938.jpg",
              "playback_position": 0,
              "pubdate": 1585061170,
              "stat": {
                "view": 98006,
                "vt": 0
              },
              "state": 0,
              "title": "恶魔果实图鉴：掌控世间灵魂的王者！跨越生死轮回的终极能力！想象空间无限大 | 作业本",
              "ugc_pay": 0,
              "vt_display": ""
            },
            {
              "aid": 97028787,
              "bvid": "BV1t7411d7im",
              "ctime": 1584469270,
              "duration": 403,
              "enable_vt": false,
              "interactive_video": false,
              "pic": "http://i2.hdslb.com/bfs/archive/352a97ac9fdaccf18d508fd9975e77168eff04fd.jpg",
              "playback_position": 0,
              "pubdate": 1584469269,
              "stat": {
                "view": 113385,
                "vt": 0
              },
              "state": 0,
              "title": "恶魔果实图鉴：价值50亿贝里！比四皇还要贵亿点点！能够授予永恒生命的恶魔果实！",
              "ugc_pay": 0,
              "vt_display": ""
            },
            {
              "aid": 92450293,
              "bvid": "BV1HE411H7jQ",
              "ctime": 1582907788,
              "duration": 338,
              "enable_vt": false,
              "interactive_video": false,
              "pic": "http://i0.hdslb.com/bfs/archive/7d0e85043d7b116e686516816bfe34561897cb87.jpg",
              "playback_position": 0,
              "pubdate": 1582907788,
              "stat": {
                "view": 158657,
                "vt": 0
              },
              "state": 0,
              "title": "恶魔果实图鉴：盘点人人果实2种型态！潜力无限大的动物系果实！",
              "ugc_pay": 0,
              "vt_display": ""
            },
            {
              "aid": 88161160,
              "bvid": "BV1W741157jo",
              "ctime": 1581398892,
              "duration": 200,
              "enable_vt": false,
              "interactive_video": false,
              "pic": "http://i2.hdslb.com/bfs/archive/5b36a4660ce5ea1819b1f95bc0c3d930c9c5d80c.jpg",
              "playback_position": 0,
              "pubdate": 1581398892,
              "stat": {
                "view": 123034,
                "vt": 0
              },
              "state": 0,
              "title": "让世界颤抖吧！最强超人系恶魔果实！觉醒后实力更加不同凡响",
              "ugc_pay": 0,
              "vt_display": ""
            }
          ],
          "meta": {
            "category": 1,
            "cover": "http://i0.hdslb.com/bfs/archive/333cf335b8c9f7d7930c404b70df8d89428dbb17.jpg",
            "creator": "",
            "ctime": 1640165352,
            "description": "",
            "keywords": [
              ""
            ],
            "last_update_ts": 1640165352,
            "mid": 488779255,
            "mtime": 1640165352,
            "name": "果实篇：人手一本恶魔果实图鉴",
            "raw_keywords": "",
            "series_id": 888045,
            "state": 2,
            "total": 9
          },
          "recent_aids": [
            967933230,
            925166199,
            98900944,
            97028787,
            92450293,
            88161160
          ]
        },
        {
          "archives": [
            {
              "aid": 95146879,
              "bvid": "BV1gE411M7hj",
              "ctime": 1583869570,
              "duration": 664,
              "enable_vt": false,
              "interactive_video": false,
              "pic": "http://i2.hdslb.com/bfs/archive/5db3bf2127e3b705e30157daa257899f5b109d23.jpg",
              "playback_position": 0,
              "pubdate": 1583869570,
              "stat": {
                "view": 77180,
                "vt": 0
              },
              "state": 0,
              "title": "海贼王早期扉页故事：艾斯溺水遭遇小萝莉！潜入海军G2化身成为海军中校！",
              "ugc_pay": 0,
              "vt_display": ""
            },
            {
              "aid": 97807462,
              "bvid": "BV1ZE411w7B3",
              "ctime": 1584728433,
              "duration": 1005,
              "enable_vt": false,
              "interactive_video": false,
              "pic": "http://i0.hdslb.com/bfs/archive/fc573a9abb351cb2d2aa9dee0a73bdd2d0b04b2b.jpg",
              "playback_position": 0,
              "pubdate": 1584728433,
              "stat": {
                "view": 68516,
                "vt": 0
              },
              "state": 0,
              "title": "海贼王精彩剧情：强者世界完整回顾！草帽团全员西装，大战传说中的海贼！",
              "ugc_pay": 0,
              "vt_display": ""
            },
            {
              "aid": 540108152,
              "bvid": "BV1yi4y1b7Xx",
              "ctime": 1585419625,
              "duration": 585,
              "enable_vt": false,
              "interactive_video": false,
              "pic": "http://i2.hdslb.com/bfs/archive/dd3f2c6f170486c00fd696bd3c8d0b75d176f498.jpg",
              "playback_position": 0,
              "pubdate": 1585419625,
              "stat": {
                "view": 154809,
                "vt": 0
              },
              "state": 0,
              "title": "海贼王扉页故事：路飞5亿赏金后，香克斯参加了婚礼，雷利开始了豪赌！世界各地还发生了什么？",
              "ugc_pay": 0,
              "vt_display": ""
            },
            {
              "aid": 93043920,
              "bvid": "BV1wE411J7wo",
              "ctime": 1583119185,
              "duration": 683,
              "enable_vt": false,
              "interactive_video": false,
              "pic": "http://i0.hdslb.com/bfs/archive/19dba28865855e8f310a1307bdb900ea58010bcf.jpg",
              "playback_position": 0,
              "pubdate": 1583119185,
              "stat": {
                "view": 68275,
                "vt": 0
              },
              "state": 0,
              "title": "海贼王扉页连载故事：海侠的一人冒险！甚平开启单人支线任务，副本奖励是一块“历史正文”！",
              "ugc_pay": 0,
              "vt_display": ""
            },
            {
              "aid": 91053156,
              "bvid": "BV1bj411f77V",
              "ctime": 1582438170,
              "duration": 514,
              "enable_vt": false,
              "interactive_video": false,
              "pic": "http://i1.hdslb.com/bfs/archive/7b2eccb8e9734e96b19d17a688b17668e44ca45c.jpg",
              "playback_position": 0,
              "pubdate": 1582438170,
              "stat": {
                "view": 99776,
                "vt": 0
              },
              "state": 0,
              "title": "海贼王前传剧情：传说中的第0话！路飞还没出生！讲述大海贼时代时代前的冒险",
              "ugc_pay": 0,
              "vt_display": ""
            },
            {
              "aid": 90069417,
              "bvid": "BV1o7411L75v",
              "ctime": 1582090180,
              "duration": 809,
              "enable_vt": false,
              "interactive_video": false,
              "pic": "http://i0.hdslb.com/bfs/archive/b327d03cd9fd3abc6b0a77c22cfd1ff137fe1f5d.jpg",
              "playback_position": 0,
              "pubdate": 1582090180,
              "stat": {
                "view": 245385,
                "vt": 0
              },
              "state": 0,
              "title": "海贼王冷门剧情：草帽一伙消失的2年间，世界各地都发生了什么？短期扉页集中连载《来自世界的甲板》｜动漫作业本",
              "ugc_pay": 0,
              "vt_display": ""
            }
          ],
          "meta": {
            "category": 1,
            "cover": "http://i2.hdslb.com/bfs/archive/5db3bf2127e3b705e30157daa257899f5b109d23.jpg",
            "creator": "",
            "ctime": 1640165352,
            "description": "",
            "keywords": [
              ""
            ],
            "last_update_ts": 1640165352,
            "mid": 488779255,
            "mtime": 1640165352,
            "name": "事件篇：海贼王重大事件回顾",
            "raw_keywords": "",
            "series_id": 888046,
            "state": 2,
            "total": 9
          },
          "recent_aids": [
            95146879,
            97807462,
            540108152,
            93043920,
            91053156,
            90069417
          ]
        },
        {
          "archives": [
            {
              "aid": 81972969,
              "bvid": "BV1fJ411j7Kv",
              "ctime": 1578078517,
              "duration": 96,
              "enable_vt": false,
              "interactive_video": false,
              "pic": "http://i0.hdslb.com/bfs/archive/ac0800021635cb69e7993f7a1a43bb81467193ce.jpg",
              "playback_position": 0,
              "pubdate": 1578078517,
              "stat": {
                "view": 27495,
                "vt": 0
              },
              "state": 0,
              "title": "路飞：不许把我的航海士弄哭！！",
              "ugc_pay": 0,
              "vt_display": ""
            }
          ],
          "meta": {
            "category": 1,
            "cover": "http://i0.hdslb.com/bfs/archive/ac0800021635cb69e7993f7a1a43bb81467193ce.jpg",
            "creator": "",
            "ctime": 1640165352,
            "description": "",
            "keywords": [
              ""
            ],
            "last_update_ts": 1640165352,
            "mid": 488779255,
            "mtime": 1640165352,
            "name": "动态漫画：海贼名场面巡礼",
            "raw_keywords": "",
            "series_id": 888047,
            "state": 2,
            "total": 1
          },
          "recent_aids": [
            81972969
          ]
        },
        {
          "archives": [
            {
              "aid": 95765946,
              "bvid": "BV1cE41157yU",
              "ctime": 1584060048,
              "duration": 849,
              "enable_vt": false,
              "interactive_video": false,
              "pic": "http://i2.hdslb.com/bfs/archive/00f7b4e421b8aac513794afefaf6875290d15bbe.jpg",
              "playback_position": 0,
              "pubdate": 1584060048,
              "stat": {
                "view": 145271,
                "vt": 0
              },
              "state": 0,
              "title": "海贼王人物志：海贼顶点！罗杰海贼团盘点！大海贼时代的开辟者！",
              "ugc_pay": 0,
              "vt_display": ""
            },
            {
              "aid": 91754947,
              "bvid": "BV1Z7411N759",
              "ctime": 1582679551,
              "duration": 549,
              "enable_vt": false,
              "interactive_video": false,
              "pic": "http://i1.hdslb.com/bfs/archive/529c142a3e7bed7653fbe1293da12449a6d4a89b.jpg",
              "playback_position": 0,
              "pubdate": 1582679551,
              "stat": {
                "view": 213184,
                "vt": 0
              },
              "state": 0,
              "title": "海贼王人物志：洛克斯海贼团盘点！8名成员以及6名潜在关联者",
              "ugc_pay": 0,
              "vt_display": ""
            },
            {
              "aid": 83499737,
              "bvid": "BV1iJ411J7iF",
              "ctime": 1579066660,
              "duration": 872,
              "enable_vt": false,
              "interactive_video": false,
              "pic": "http://i2.hdslb.com/bfs/archive/901ee4b72dc46f93fee9948d00e227ddafbf5cc3.jpg",
              "playback_position": 0,
              "pubdate": 1579066660,
              "stat": {
                "view": 99553,
                "vt": 0
              },
              "state": 0,
              "title": "偶像练习生、格斗家、强盗、还有二愣子！盘点五皇路飞登顶海贼王的班底，憨憨大集合！",
              "ugc_pay": 0,
              "vt_display": ""
            },
            {
              "aid": 82012899,
              "bvid": "BV13J41177vY",
              "ctime": 1578118242,
              "duration": 523,
              "enable_vt": false,
              "interactive_video": false,
              "pic": "http://i2.hdslb.com/bfs/archive/e44d1c6bba7c49a8afffec0d41a6363f1e92765a.jpg",
              "playback_position": 0,
              "pubdate": 1578118242,
              "stat": {
                "view": 114431,
                "vt": 0
              },
              "state": 0,
              "title": "世界最凶恶罪犯？海贼王看似最中立的组织，却以颠覆世界为目标！",
              "ugc_pay": 0,
              "vt_display": ""
            },
            {
              "aid": 81555594,
              "bvid": "BV1EJ411b7uU",
              "ctime": 1577838398,
              "duration": 534,
              "enable_vt": false,
              "interactive_video": false,
              "pic": "http://i1.hdslb.com/bfs/archive/a45822f80814726dfc19b9ebf88de99e270624c9.jpg",
              "playback_position": 0,
              "pubdate": 1577838398,
              "stat": {
                "view": 121228,
                "vt": 0
              },
              "state": 0,
              "title": "超新星：穷凶极恶？诞生于新旧时代的夹缝，背负战乱命运的问题人物！",
              "ugc_pay": 0,
              "vt_display": ""
            },
            {
              "aid": 80868251,
              "bvid": "BV1DJ411Y7pS",
              "ctime": 1577443021,
              "duration": 721,
              "enable_vt": false,
              "interactive_video": false,
              "pic": "http://i1.hdslb.com/bfs/archive/a68361cda3fe0b5a0605b6d7a2683db589df84bb.jpg",
              "playback_position": 0,
              "pubdate": 1577443021,
              "stat": {
                "view": 166155,
                "vt": 0
              },
              "state": 0,
              "title": "【动漫盘点】海军本部：以“绝对正义”之名！真正的海上霸者",
              "ugc_pay": 0,
              "vt_display": ""
            }
          ],
          "meta": {
            "category": 1,
            "cover": "http://i2.hdslb.com/bfs/archive/00f7b4e421b8aac513794afefaf6875290d15bbe.jpg",
            "creator": "",
            "ctime": 1640165352,
            "description": "",
            "keywords": [
              ""
            ],
            "last_update_ts": 1640165352,
            "mid": 488779255,
            "mtime": 1640165352,
            "name": "人物篇：盘点海贼王里面的神仙大佬们",
            "raw_keywords": "",
            "series_id": 888048,
            "state": 2,
            "total": 8
          },
          "recent_aids": [
            95765946,
            91754947,
            83499737,
            82012899,
            81555594,
            80868251
          ]
        },
        {
          "archives": [
            {
              "aid": 84664610,
              "bvid": "BV1o7411e7pu",
              "ctime": 1579750245,
              "duration": 454,
              "enable_vt": false,
              "interactive_video": false,
              "pic": "http://i0.hdslb.com/bfs/archive/b5d30fa708c637fbe3bfa488d1ccf17d456ca770.jpg",
              "playback_position": 0,
              "pubdate": 1579750245,
              "stat": {
                "view": 167320,
                "vt": 0
              },
              "state": 0,
              "title": "海贼王补习：包含5把无上大快刀！所有目前已登场的名刀一口气看完",
              "ugc_pay": 0,
              "vt_display": ""
            },
            {
              "aid": 540258914,
              "bvid": "BV1ki4y187AU",
              "ctime": 1587146970,
              "duration": 725,
              "enable_vt": false,
              "interactive_video": false,
              "pic": "http://i0.hdslb.com/bfs/archive/b9ebc673359266f7a3a77684579b1d228cf64c55.jpg",
              "playback_position": 0,
              "pubdate": 1587146970,
              "stat": {
                "view": 109428,
                "vt": 0
              },
              "state": 0,
              "title": "海贼王器物盘点：万里阳光号内部结构大揭秘！最完整的船体分析",
              "ugc_pay": 0,
              "vt_display": ""
            }
          ],
          "meta": {
            "category": 1,
            "cover": "http://i0.hdslb.com/bfs/archive/b5d30fa708c637fbe3bfa488d1ccf17d456ca770.jpg",
            "creator": "",
            "ctime": 1640165351,
            "description": "",
            "keywords": [
              ""
            ],
            "last_update_ts": 1640165351,
            "mid": 488779255,
            "mtime": 1640165351,
            "name": "器物篇：海贼王神兵利器与秘宝盘点",
            "raw_keywords": "",
            "series_id": 888042,
            "state": 2,
            "total": 2
          },
          "recent_aids": [
            84664610,
            540258914
          ]
        },
        {
          "archives": [
            {
              "aid": 93609417,
              "bvid": "BV14E411s7Lq",
              "ctime": 1583334323,
              "duration": 598,
              "enable_vt": false,
              "interactive_video": false,
              "pic": "http://i1.hdslb.com/bfs/archive/67d650902bd4dd7fc11e0efbcba7235d239ad78c.jpg",
              "playback_position": 0,
              "pubdate": 1583334323,
              "stat": {
                "view": 79199,
                "vt": 0
              },
              "state": 0,
              "title": "海贼王精华盘点：连载二十年，10大令人难忘的瞬间！“艾斯之死”排第4位",
              "ugc_pay": 0,
              "vt_display": ""
            },
            {
              "aid": 752860512,
              "bvid": "BV1Dk4y1R7zA",
              "ctime": 1586888348,
              "duration": 817,
              "enable_vt": false,
              "interactive_video": false,
              "pic": "http://i2.hdslb.com/bfs/archive/dd8a7e971649ec7d67b745f68e202c8c7ce46738.jpg",
              "playback_position": 0,
              "pubdate": 1586888348,
              "stat": {
                "view": 116192,
                "vt": 0
              },
              "state": 0,
              "title": "海贼王动画盘点：连载20年完整观影指南！一口气回顾900多集动画",
              "ugc_pay": 0,
              "vt_display": ""
            },
            {
              "aid": 242843709,
              "bvid": "BV1Ee411s7nK",
              "ctime": 1587523965,
              "duration": 642,
              "enable_vt": false,
              "interactive_video": false,
              "pic": "http://i0.hdslb.com/bfs/archive/a23fa0446daad11746d1001a5ed4873d493e7aad.jpg",
              "playback_position": 0,
              "pubdate": 1587523965,
              "stat": {
                "view": 92755,
                "vt": 0
              },
              "state": 0,
              "title": "海贼王剧情盘点：14部剧场版电影完整回顾！一口气看完那些经典",
              "ugc_pay": 0,
              "vt_display": ""
            },
            {
              "aid": 96603431,
              "bvid": "BV1z7411f7nq",
              "ctime": 1584331719,
              "duration": 257,
              "enable_vt": false,
              "interactive_video": false,
              "pic": "http://i0.hdslb.com/bfs/archive/a5ff2b98172ee19f5d1269bddcd1edb5e1e680cb.jpg",
              "playback_position": 0,
              "pubdate": 1584331719,
              "stat": {
                "view": 44434,
                "vt": 0
              },
              "state": 0,
              "title": "海贼王924集剧情速看！大招牌“炎灾”烬终于出手！山治秘密武器即将发动",
              "ugc_pay": 0,
              "vt_display": ""
            },
            {
              "aid": 98499263,
              "bvid": "BV1uE411c7MM",
              "ctime": 1584937139,
              "duration": 268,
              "enable_vt": false,
              "interactive_video": false,
              "pic": "http://i0.hdslb.com/bfs/archive/c68a7acdb46f9dbf55123abc1f17a7eaaf07f171.jpg",
              "playback_position": 0,
              "pubdate": 1584937139,
              "stat": {
                "view": 36953,
                "vt": 0
              },
              "state": 0,
              "title": "海贼王925集剧情速看！山治街头华丽变身，大型真香现场来了",
              "ugc_pay": 0,
              "vt_display": ""
            },
            {
              "aid": 837584094,
              "bvid": "BV1dg4y1b7FV",
              "ctime": 1585509270,
              "duration": 258,
              "enable_vt": false,
              "interactive_video": false,
              "pic": "http://i2.hdslb.com/bfs/archive/e14283d37ab4e314f1565810637b0a3c180be134.jpg",
              "playback_position": 0,
              "pubdate": 1585509270,
              "stat": {
                "view": 35073,
                "vt": 0
              },
              "state": 0,
              "title": "海贼王926集剧情速看！大妈落水失忆，罗宾绝处逢生！将军府内暗流涌动",
              "ugc_pay": 0,
              "vt_display": ""
            }
          ],
          "meta": {
            "category": 1,
            "cover": "http://i1.hdslb.com/bfs/archive/67d650902bd4dd7fc11e0efbcba7235d239ad78c.jpg",
            "creator": "",
            "ctime": 1640165351,
            "description": "",
            "keywords": [
              ""
            ],
            "last_update_ts": 1640165351,
            "mid": 488779255,
            "mtime": 1640165352,
            "name": "剧情篇：海贼王精彩剧情盘点与解析",
            "raw_keywords": "",
            "series_id": 888043,
            "state": 2,
            "total": 13
          },
          "recent_aids": [
            93609417,
            752860512,
            242843709,
            96603431,
            98499263,
            837584094
          ]
        }
      ]
    }
  }
}
```

### 返回结果

|状态码|状态码含义|说明|数据模型|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|成功|Inline|

### 返回数据结构

状态码 **200**

|名称|类型|必选|约束|中文名|说明|
|---|---|---|---|---|---|
|» code|integer|true|none||none|
|» message|string|true|none||none|
|» ttl|integer|true|none||none|
|» data|object|true|none||none|
|»» items_lists|object|true|none||none|
|»»» page|object|true|none||none|
|»»»» page_num|integer|true|none||none|
|»»»» page_size|integer|true|none||none|
|»»»» total|integer|true|none||none|
|»»» seasons_list|[object]|true|none|视频列表|none|
|»»»» archives|[object]|true|none||none|
|»»»»» aid|integer|true|none||none|
|»»»»» bvid|string|true|none||none|
|»»»»» ctime|integer|true|none||none|
|»»»»» duration|integer|true|none||none|
|»»»»» enable_vt|boolean|true|none||none|
|»»»»» interactive_video|boolean|true|none||none|
|»»»»» pic|string|true|none||none|
|»»»»» playback_position|integer|true|none||none|
|»»»»» pubdate|integer|true|none||none|
|»»»»» stat|object|true|none||none|
|»»»»»» view|integer|true|none||none|
|»»»»»» vt|integer|true|none||none|
|»»»»» state|integer|true|none||none|
|»»»»» title|string|true|none||none|
|»»»»» ugc_pay|integer|true|none||none|
|»»»»» vt_display|string|true|none||none|
|»»»» meta|object|true|none||none|
|»»»»» category|integer|true|none||none|
|»»»»» cover|string|true|none||none|
|»»»»» description|string|true|none||none|
|»»»»» mid|integer|true|none||none|
|»»»»» name|string|true|none||none|
|»»»»» ptime|integer|true|none||none|
|»»»»» season_id|integer|true|none||none|
|»»»»» total|integer|true|none||none|
|»»»» recent_aids|[integer]|true|none||none|
|»»» series_list|[object]|true|none|合集列表|none|
|»»»» archives|[object]|true|none||none|
|»»»»» aid|integer|true|none||none|
|»»»»» bvid|string|true|none||none|
|»»»»» ctime|integer|true|none||none|
|»»»»» duration|integer|true|none||none|
|»»»»» enable_vt|boolean|true|none||none|
|»»»»» interactive_video|boolean|true|none||none|
|»»»»» pic|string|true|none||none|
|»»»»» playback_position|integer|true|none||none|
|»»»»» pubdate|integer|true|none||none|
|»»»»» stat|object|true|none||none|
|»»»»»» view|integer|true|none||none|
|»»»»»» vt|integer|true|none||none|
|»»»»» state|integer|true|none||none|
|»»»»» title|string|true|none||none|
|»»»»» ugc_pay|integer|true|none||none|
|»»»»» vt_display|string|true|none||none|
|»»»» meta|object|true|none||none|
|»»»»» category|integer|true|none||none|
|»»»»» cover|string|true|none||none|
|»»»»» creator|string|true|none||none|
|»»»»» ctime|integer|true|none||none|
|»»»»» description|string|true|none||none|
|»»»»» keywords|[string]|true|none||none|
|»»»»» last_update_ts|integer|true|none||none|
|»»»»» mid|integer|true|none||none|
|»»»»» mtime|integer|true|none||none|
|»»»»» name|string|true|none||none|
|»»»»» raw_keywords|string|true|none||none|
|»»»»» series_id|integer|true|none||none|
|»»»»» state|integer|true|none||none|
|»»»»» total|integer|true|none||none|
|»»»» recent_aids|[integer]|true|none||none|

## GET 公告信息

GET /x/space/notice

### 请求参数

|名称|位置|类型|必选|说明|
|---|---|---|---|---|
|mid|query|string| 否 |none|
|User-Agent|header|string| 否 |none|

> 返回示例

> 200 Response

```json
{
  "code": 0,
  "message": "string",
  "ttl": 0,
  "data": "string"
}
```

### 返回结果

|状态码|状态码含义|说明|数据模型|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|成功|Inline|

### 返回数据结构

状态码 **200**

|名称|类型|必选|约束|中文名|说明|
|---|---|---|---|---|---|
|» code|integer|true|none||none|
|» message|string|true|none||none|
|» ttl|integer|true|none||none|
|» data|string|true|none||none|

## GET 本月充电

GET /x/ugcpay-rank/elec/month/up

### 请求参数

|名称|位置|类型|必选|说明|
|---|---|---|---|---|
|up_mid|query|string| 否 |none|
|User-Agent|header|string| 否 |none|

> 返回示例

> 200 Response

```json
{
  "code": 0,
  "message": "string",
  "ttl": 0,
  "data": {
    "count": 0,
    "list": [
      {
        "uname": "string",
        "avatar": "string",
        "mid": 0,
        "pay_mid": 0,
        "rank": 0,
        "trend_type": 0,
        "vip_info": {
          "vipDueMsec": 0,
          "vipStatus": 0,
          "vipType": 0
        },
        "message": "string",
        "message_hidden": 0
      }
    ],
    "total_count": 0,
    "total": 0,
    "special_day": 0
  }
}
```

### 返回结果

|状态码|状态码含义|说明|数据模型|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|成功|Inline|

### 返回数据结构

状态码 **200**

|名称|类型|必选|约束|中文名|说明|
|---|---|---|---|---|---|
|» code|integer|true|none||none|
|» message|string|true|none||none|
|» ttl|integer|true|none||none|
|» data|object|true|none||none|
|»» count|integer|true|none||none|
|»» list|[object]|true|none||none|
|»»» uname|string|true|none||none|
|»»» avatar|string|true|none||none|
|»»» mid|integer|true|none||none|
|»»» pay_mid|integer|true|none||none|
|»»» rank|integer|true|none||none|
|»»» trend_type|integer|true|none||none|
|»»» vip_info|object|true|none||none|
|»»»» vipDueMsec|integer|true|none||none|
|»»»» vipStatus|integer|true|none||none|
|»»»» vipType|integer|true|none||none|
|»»» message|string|true|none||none|
|»»» message_hidden|integer|true|none||none|
|»» total_count|integer|true|none||none|
|»» total|integer|true|none||none|
|»» special_day|integer|true|none||none|

## GET 代表作品

GET /x/space/masterpiece

### 请求参数

|名称|位置|类型|必选|说明|
|---|---|---|---|---|
|vmid|query|string| 否 |用户id|
|User-Agent|header|string| 否 |none|

> 返回示例

> 200 Response

```json
{}
```

### 返回结果

|状态码|状态码含义|说明|数据模型|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|成功|Inline|

### 返回数据结构

## GET 置顶作品

GET /x/space/top/arc

### 请求参数

|名称|位置|类型|必选|说明|
|---|---|---|---|---|
|vmid|query|string| 否 |用户id|
|User-Agent|header|string| 否 |none|

> 返回示例

> 200 Response

```json
{
  "code": 0,
  "message": "string",
  "ttl": 0,
  "data": {
    "aid": 0,
    "videos": 0,
    "tid": 0,
    "tname": "string",
    "copyright": 0,
    "pic": "string",
    "title": "string",
    "pubdate": 0,
    "ctime": 0,
    "desc": "string",
    "state": 0,
    "duration": 0,
    "rights": {
      "bp": 0,
      "elec": 0,
      "download": 0,
      "movie": 0,
      "pay": 0,
      "hd5": 0,
      "no_reprint": 0,
      "autoplay": 0,
      "ugc_pay": 0,
      "is_cooperation": 0,
      "ugc_pay_preview": 0,
      "no_background": 0,
      "arc_pay": 0,
      "pay_free_watch": 0
    },
    "owner": {
      "mid": 0,
      "name": "string",
      "face": "string"
    },
    "stat": {
      "aid": 0,
      "view": 0,
      "danmaku": 0,
      "reply": 0,
      "favorite": 0,
      "coin": 0,
      "share": 0,
      "now_rank": 0,
      "his_rank": 0,
      "like": 0,
      "dislike": 0,
      "vt": 0,
      "vv": 0
    },
    "dynamic": "string",
    "cid": 0,
    "dimension": {
      "width": 0,
      "height": 0,
      "rotate": 0
    },
    "short_link_v2": "string",
    "bvid": "string",
    "reason": "string",
    "inter_video": true,
    "is_charging_arc": true,
    "enable_vt": 0,
    "playback_position": 0
  }
}
```

### 返回结果

|状态码|状态码含义|说明|数据模型|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|成功|Inline|

### 返回数据结构

状态码 **200**

|名称|类型|必选|约束|中文名|说明|
|---|---|---|---|---|---|
|» code|integer|true|none||none|
|» message|string|true|none||none|
|» ttl|integer|true|none||none|
|» data|object|true|none||none|
|»» aid|integer|true|none||none|
|»» videos|integer|true|none||none|
|»» tid|integer|true|none||none|
|»» tname|string|true|none||none|
|»» copyright|integer|true|none||none|
|»» pic|string|true|none||none|
|»» title|string|true|none||none|
|»» pubdate|integer|true|none||none|
|»» ctime|integer|true|none||none|
|»» desc|string|true|none||none|
|»» state|integer|true|none||none|
|»» duration|integer|true|none||none|
|»» rights|object|true|none||none|
|»»» bp|integer|true|none||none|
|»»» elec|integer|true|none||none|
|»»» download|integer|true|none||none|
|»»» movie|integer|true|none||none|
|»»» pay|integer|true|none||none|
|»»» hd5|integer|true|none||none|
|»»» no_reprint|integer|true|none||none|
|»»» autoplay|integer|true|none||none|
|»»» ugc_pay|integer|true|none||none|
|»»» is_cooperation|integer|true|none||none|
|»»» ugc_pay_preview|integer|true|none||none|
|»»» no_background|integer|true|none||none|
|»»» arc_pay|integer|true|none||none|
|»»» pay_free_watch|integer|true|none||none|
|»» owner|object|true|none||none|
|»»» mid|integer|true|none||none|
|»»» name|string|true|none||none|
|»»» face|string|true|none||none|
|»» stat|object|true|none||none|
|»»» aid|integer|true|none||none|
|»»» view|integer|true|none||none|
|»»» danmaku|integer|true|none||none|
|»»» reply|integer|true|none||none|
|»»» favorite|integer|true|none||none|
|»»» coin|integer|true|none||none|
|»»» share|integer|true|none||none|
|»»» now_rank|integer|true|none||none|
|»»» his_rank|integer|true|none||none|
|»»» like|integer|true|none||none|
|»»» dislike|integer|true|none||none|
|»»» vt|integer|true|none||none|
|»»» vv|integer|true|none||none|
|»» dynamic|string|true|none||none|
|»» cid|integer|true|none||none|
|»» dimension|object|true|none||none|
|»»» width|integer|true|none||none|
|»»» height|integer|true|none||none|
|»»» rotate|integer|true|none||none|
|»» short_link_v2|string|true|none||none|
|»» bvid|string|true|none||none|
|»» reason|string|true|none||none|
|»» inter_video|boolean|true|none||none|
|»» is_charging_arc|boolean|true|none||none|
|»» enable_vt|integer|true|none||none|
|»» playback_position|integer|true|none||none|

## GET 投稿统计 (无需登录)

GET /x/space/navnum

### 请求参数

|名称|位置|类型|必选|说明|
|---|---|---|---|---|
|mid|query|string| 否 |none|
|User-Agent|header|string| 否 |none|

> 返回示例

> 200 Response

```json
{
  "code": 0,
  "message": "string",
  "ttl": 0,
  "data": {
    "video": 0,
    "bangumi": 0,
    "cinema": 0,
    "channel": {
      "master": 0,
      "guest": 0
    },
    "favourite": {
      "master": 0,
      "guest": 0
    },
    "tag": 0,
    "article": 0,
    "playlist": 0,
    "album": 0,
    "audio": 0,
    "pugv": 0,
    "season_num": 0
  }
}
```

### 返回结果

|状态码|状态码含义|说明|数据模型|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|成功|Inline|

### 返回数据结构

状态码 **200**

|名称|类型|必选|约束|中文名|说明|
|---|---|---|---|---|---|
|» code|integer|true|none||none|
|» message|string|true|none||none|
|» ttl|integer|true|none||none|
|» data|object|true|none||none|
|»» video|integer|true|none||none|
|»» bangumi|integer|true|none||none|
|»» cinema|integer|true|none||none|
|»» channel|object|true|none||none|
|»»» master|integer|true|none||none|
|»»» guest|integer|true|none||none|
|»» favourite|object|true|none||none|
|»»» master|integer|true|none||none|
|»»» guest|integer|true|none||none|
|»» tag|integer|true|none||none|
|»» article|integer|true|none||none|
|»» playlist|integer|true|none||none|
|»» album|integer|true|none||none|
|»» audio|integer|true|none||none|
|»» pugv|integer|true|none||none|
|»» season_num|integer|true|none||none|

## POST 修改关系 (关注或取消关注)

POST /x/relation/modify

> Body 请求参数

```yaml
fid: " 433351"
act: "2"
re_src: " 11"
csrf: f3defc067cb3fa8f3580c5248fdf0940

```

### 请求参数

|名称|位置|类型|必选|说明|
|---|---|---|---|---|
|Cookie|header|string| 否 |none|
|Referer|header|string| 否 |none|
|User-Agent|header|string| 否 |none|
|body|body|object| 否 |none|
|» fid|body|string| 否 |要关注或取消的用户id|
|» act|body|string| 否 |1关注, 2取消关注, 3悄悄关注, 4取消悄悄关注|
|» re_src|body|string| 否 |none|
|» csrf|body|string| 否 |这个就是cookie中的bili_jct|

> 返回示例

> 200 Response

```json
{
  "code": 0,
  "message": "string",
  "ttl": 0
}
```

### 返回结果

|状态码|状态码含义|说明|数据模型|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|成功|Inline|

### 返回数据结构

状态码 **200**

|名称|类型|必选|约束|中文名|说明|
|---|---|---|---|---|---|
|» code|integer|true|none||none|
|» message|string|true|none||none|
|» ttl|integer|true|none||none|

## POST 修改资料

POST /x/member/web/update

> Body 请求参数

```yaml
birthday: 2003-09-17
csrf: f3defc067cb3fa8f3580c5248fdf0940
sex: " 男"
uname: a14n
usersign: string

```

### 请求参数

|名称|位置|类型|必选|说明|
|---|---|---|---|---|
|SESSDATA|cookie|string| 是 |none|
|User-Agent|header|string| 否 |none|
|body|body|object| 否 |none|
|» birthday|body|string| 否 |出生日期|
|» csrf|body|string| 否 |cookie中的bili_jct|
|» sex|body|string| 否 |性别|
|» uname|body|string| 否 |用户名|
|» usersign|body|string| 否 |签名|

> 返回示例

> 200 Response

```json
{
  "code": 0,
  "message": "string",
  "ttl": 0
}
```

### 返回结果

|状态码|状态码含义|说明|数据模型|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|成功|Inline|

### 返回数据结构

状态码 **200**

|名称|类型|必选|约束|中文名|说明|
|---|---|---|---|---|---|
|» code|integer|true|none||none|
|» message|string|true|none||none|
|» ttl|integer|true|none||none|

## POST 更新头像

POST /x/member/web/face/update

> Body 请求参数

```yaml
face: file://C:\Users\a14n\Downloads\b4e08d394ace1dda4fa731f105bf7efe5a3b6ec3.jpg@150w_150h.jpg
dopost: save

```

### 请求参数

|名称|位置|类型|必选|说明|
|---|---|---|---|---|
|SESSDATA|cookie|string| 否 |none|
|csrf|query|string| 否 |Cookie中的bili_jct|
|User-Agent|header|string| 否 |none|
|body|body|object| 否 |none|
|» face|body|string(binary)| 否 |头像文件|
|» dopost|body|string| 否 |none|

> 返回示例

> 200 Response

```json
{}
```

### 返回结果

|状态码|状态码含义|说明|数据模型|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|成功|Inline|

### 返回数据结构

## GET 硬币记录

GET /x/member/web/coin/log

### 请求参数

|名称|位置|类型|必选|说明|
|---|---|---|---|---|
|SESSDATA|cookie|string| 否 |none|
|csrf|query|string| 否 |none|
|jsonp|query|string| 否 |none|
|User-Agent|header|string| 否 |none|

> 返回示例

> 200 Response

```json
{
  "code": 0,
  "message": "string",
  "ttl": 0,
  "data": {
    "list": [
      {
        "time": "string",
        "delta": 0,
        "reason": "string"
      }
    ],
    "count": 0
  }
}
```

### 返回结果

|状态码|状态码含义|说明|数据模型|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|成功|Inline|

### 返回数据结构

状态码 **200**

|名称|类型|必选|约束|中文名|说明|
|---|---|---|---|---|---|
|» code|integer|true|none||none|
|» message|string|true|none||none|
|» ttl|integer|true|none||none|
|» data|object|true|none||none|
|»» list|[object]|true|none||none|
|»»» time|string|true|none||none|
|»»» delta|integer|true|none||none|
|»»» reason|string|true|none||none|
|»» count|integer|true|none||none|

## GET 登录记录

GET /x/member/web/login/log

### 请求参数

|名称|位置|类型|必选|说明|
|---|---|---|---|---|
|SESSDATA|cookie|string| 否 |none|
|csrf|query|string| 否 |none|
|jsonp|query|string| 否 |none|
|User-Agent|header|string| 否 |none|

> 返回示例

> 200 Response

```json
{
  "code": 0,
  "message": "string",
  "ttl": 0,
  "data": {
    "count": 0,
    "list": [
      {
        "ip": "string",
        "time": 0,
        "time_at": "string",
        "status": true,
        "type": 0,
        "geo": "string"
      }
    ]
  }
}
```

### 返回结果

|状态码|状态码含义|说明|数据模型|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|成功|Inline|

### 返回数据结构

状态码 **200**

|名称|类型|必选|约束|中文名|说明|
|---|---|---|---|---|---|
|» code|integer|true|none||none|
|» message|string|true|none||none|
|» ttl|integer|true|none||none|
|» data|object|true|none||none|
|»» count|integer|true|none||none|
|»» list|[object]|true|none||none|
|»»» ip|string|true|none||none|
|»»» time|integer|true|none||none|
|»»» time_at|string|true|none||none|
|»»» status|boolean|true|none||none|
|»»» type|integer|true|none||none|
|»»» geo|string|true|none||none|

## GET 节操记录

GET /x/member/web/moral/log

### 请求参数

|名称|位置|类型|必选|说明|
|---|---|---|---|---|
|SESSDATA|cookie|string| 否 |none|
|csrf|query|string| 否 |none|
|jsonp|query|string| 否 |none|
|User-Agent|header|string| 否 |none|

> 返回示例

> 200 Response

```json
{
  "code": 0,
  "message": "string",
  "ttl": 0,
  "data": {
    "moral": 0,
    "list": [
      "string"
    ],
    "count": 0
  }
}
```

### 返回结果

|状态码|状态码含义|说明|数据模型|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|成功|Inline|

### 返回数据结构

状态码 **200**

|名称|类型|必选|约束|中文名|说明|
|---|---|---|---|---|---|
|» code|integer|true|none||none|
|» message|string|true|none||none|
|» ttl|integer|true|none||none|
|» data|object|true|none||none|
|»» moral|integer|true|none||none|
|»» list|[string]|true|none||none|
|»» count|integer|true|none||none|

## GET 积分记录 (大会员)

GET /x/point/history

### 请求参数

|名称|位置|类型|必选|说明|
|---|---|---|---|---|
|SESSDATA|cookie|string| 否 |none|
|csrf|query|string| 否 |none|
|pn|query|string| 否 |none|
|ps|query|string| 否 |none|
|User-Agent|header|string| 否 |none|

> 返回示例

> 200 Response

```json
{
  "code": 0,
  "message": "string",
  "ttl": 0,
  "data": {
    "phs": null,
    "total": 0
  }
}
```

### 返回结果

|状态码|状态码含义|说明|数据模型|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|成功|Inline|

### 返回数据结构

状态码 **200**

|名称|类型|必选|约束|中文名|说明|
|---|---|---|---|---|---|
|» code|integer|true|none||none|
|» message|string|true|none||none|
|» ttl|integer|true|none||none|
|» data|object|true|none||none|
|»» phs|null|true|none||none|
|»» total|integer|true|none||none|

## GET 每日奖励

GET /x/member/web/exp/reward

### 请求参数

|名称|位置|类型|必选|说明|
|---|---|---|---|---|
|SESSDATA|cookie|string| 否 |none|
|csrf|query|string| 否 |none|
|User-Agent|header|string| 否 |none|

> 返回示例

> 200 Response

```json
{
  "code": 0,
  "message": "string",
  "ttl": 0,
  "data": {
    "login": true,
    "watch": true,
    "coins": 0,
    "share": true,
    "email": true,
    "tel": true,
    "safe_question": true,
    "identify_card": true
  }
}
```

### 返回结果

|状态码|状态码含义|说明|数据模型|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|成功|Inline|

### 返回数据结构

状态码 **200**

|名称|类型|必选|约束|中文名|说明|
|---|---|---|---|---|---|
|» code|integer|true|none||none|
|» message|string|true|none||none|
|» ttl|integer|true|none||none|
|» data|object|true|none||none|
|»» login|boolean|true|none||none|
|»» watch|boolean|true|none||none|
|»» coins|integer|true|none||none|
|»» share|boolean|true|none||none|
|»» email|boolean|true|none||none|
|»» tel|boolean|true|none||none|
|»» safe_question|boolean|true|none||none|
|»» identify_card|boolean|true|none||none|

# 热门

## GET 热门列表 (微信小程序)

GET /x/web-interface/wx/hot

### 请求参数

|名称|位置|类型|必选|说明|
|---|---|---|---|---|
|platform|query|string| 否 |none|
|User-Agent|header|string| 否 |none|

> 返回示例

> 成功

```json
{
  "code": 0,
  "data": [
    {
      "aid": 577486541,
      "type_id": 253,
      "tname": "动漫杂谈",
      "pic": "http://i0.hdslb.com/bfs/archive/17c6d6e71cb389f1fd62afd299254823f8bb9cd0.jpg",
      "title": "我用了太长的时间，终于把宫崎骏和国漫这条最恶毒的谣言辟谣了",
      "pubdate": 1697855400,
      "ctime": 1697814335,
      "tags": [],
      "duration": 229,
      "author": {
        "mid": 6989892,
        "name": "哎呀老付",
        "face": "https://i0.hdslb.com/bfs/face/853d5e2f9c6227c92d78b9531b31db53aa580209.jpg"
      },
      "stat": {
        "aid": 577486541,
        "view": 900076,
        "danmaku": 946,
        "reply": 2999,
        "favorite": 32341,
        "coin": 89140,
        "share": 3665,
        "now_rank": 0,
        "his_rank": 7,
        "like": 147914,
        "dislike": 0,
        "vt": 0,
        "vv": 900076
      },
      "hot_desc": "14万点赞",
      "corner_mark": 0,
      "bvid": "BV1KB4y1Z7jm",
      "enable_vt": 0,
      "vt_display": ""
    },
    {
      "aid": 492476595,
      "type_id": 47,
      "tname": "短片·手书",
      "pic": "http://i0.hdslb.com/bfs/archive/0adc342ffc6d27dd067b06dce4981323b96300e7.jpg",
      "title": "【重返未来1999 | 独立原创动画】万物理论 - 𝐓𝐡𝐞 𝐓𝐡𝐞𝐨𝐫𝐲 𝐎𝐟 𝐄𝐯𝐞𝐫𝐲𝐭𝐡𝐢𝐧𝐠【VIV】",
      "pubdate": 1697855400,
      "ctime": 1697787883,
      "tags": [],
      "duration": 119,
      "author": {
        "mid": 1207265987,
        "name": "___viv___",
        "face": "https://i2.hdslb.com/bfs/face/df74ecae4e45517a267ec9cb54d712c4dee5897b.jpg"
      },
      "stat": {
        "aid": 492476595,
        "view": 1436576,
        "danmaku": 963,
        "reply": 3010,
        "favorite": 80910,
        "coin": 91870,
        "share": 19041,
        "now_rank": 0,
        "his_rank": 8,
        "like": 198294,
        "dislike": 0,
        "vt": 0,
        "vv": 1436576
      },
      "hot_desc": "百万播放",
      "corner_mark": 0,
      "bvid": "BV1BN411x74s",
      "enable_vt": 0,
      "vt_display": ""
    },
    {
      "aid": 619955841,
      "type_id": 130,
      "tname": "音乐综合",
      "pic": "http://i2.hdslb.com/bfs/archive/d2236476981c25bfc692efdf05bcf40cbc49a2ea.jpg",
      "title": "在学校唱《谁是我的新郎》被校领导追杀",
      "pubdate": 1697860800,
      "ctime": 1697795283,
      "tags": [],
      "duration": 274,
      "author": {
        "mid": 1723817,
        "name": "樱萍Apple",
        "face": "https://i2.hdslb.com/bfs/face/6e0fa1bdbbf7e0dd929d968df3b57ca99d187e25.jpg"
      },
      "stat": {
        "aid": 619955841,
        "view": 658787,
        "danmaku": 1811,
        "reply": 1407,
        "favorite": 1535,
        "coin": 3527,
        "share": 2284,
        "now_rank": 0,
        "his_rank": 0,
        "like": 33587,
        "dislike": 0,
        "vt": 0,
        "vv": 658787
      },
      "hot_desc": "",
      "corner_mark": 0,
      "bvid": "BV1N84y1o79p",
      "enable_vt": 0,
      "vt_display": ""
    },
    {
      "aid": 277425830,
      "type_id": 138,
      "tname": "搞笑",
      "pic": "http://i1.hdslb.com/bfs/archive/a65028e174e28a413e100b0b6cd2a5846005b13e.jpg",
      "title": "小傲吃遍全宇宙【国际篇】",
      "pubdate": 1697860800,
      "ctime": 1697827540,
      "tags": [],
      "duration": 2022,
      "author": {
        "mid": 446430908,
        "name": "小傲想睡觉",
        "face": "https://i2.hdslb.com/bfs/face/ff50c7ace4ffc66eac2bafcca8b91ca29cd80ad5.jpg"
      },
      "stat": {
        "aid": 277425830,
        "view": 747160,
        "danmaku": 13409,
        "reply": 2391,
        "favorite": 24157,
        "coin": 69515,
        "share": 1979,
        "now_rank": 0,
        "his_rank": 16,
        "like": 114965,
        "dislike": 0,
        "vt": 0,
        "vv": 747160
      },
      "hot_desc": "11万点赞",
      "corner_mark": 1,
      "bvid": "BV1Ew411F7G8",
      "enable_vt": 0,
      "vt_display": ""
    },
    {
      "aid": 322421925,
      "type_id": 176,
      "tname": "汽车生活",
      "pic": "http://i0.hdslb.com/bfs/archive/c01d2f66e512bb8d747d889c764ae736d536b51f.jpg",
      "title": "《送你一箱油》之半挂车的一箱油竟然这么多！",
      "pubdate": 1697800058,
      "ctime": 1697800058,
      "tags": [],
      "duration": 105,
      "author": {
        "mid": 3546386366728194,
        "name": "小雨玩车",
        "face": "https://i0.hdslb.com/bfs/face/ef875e957ea88e4ace6320a8e2e51006cf3bcb5a.jpg"
      },
      "stat": {
        "aid": 322421925,
        "view": 1372092,
        "danmaku": 438,
        "reply": 875,
        "favorite": 5152,
        "coin": 16604,
        "share": 127,
        "now_rank": 0,
        "his_rank": 72,
        "like": 171923,
        "dislike": 0,
        "vt": 0,
        "vv": 1372092
      },
      "hot_desc": "百万播放",
      "corner_mark": 1,
      "bvid": "BV1fw41167dK",
      "enable_vt": 0,
      "vt_display": ""
    },
    {
      "aid": 534890025,
      "type_id": 201,
      "tname": "科学科普",
      "pic": "http://i2.hdslb.com/bfs/archive/cf3d5af81d51d5ac0952e08b4708342b1a7f80b8.jpg",
      "title": "一位健美运动员不慎摄入了超大量的壮阳药，这是他的大脑发生的变化",
      "pubdate": 1697863444,
      "ctime": 1697863444,
      "tags": [],
      "duration": 1007,
      "author": {
        "mid": 297786973,
        "name": "Chubbyemu",
        "face": "https://i1.hdslb.com/bfs/face/5819f8d18f6dfa7841b4ca79902e7608f06bd49f.jpg"
      },
      "stat": {
        "aid": 534890025,
        "view": 654274,
        "danmaku": 4982,
        "reply": 1813,
        "favorite": 7652,
        "coin": 15284,
        "share": 5873,
        "now_rank": 0,
        "his_rank": 0,
        "like": 61334,
        "dislike": 0,
        "vt": 0,
        "vv": 654274
      },
      "hot_desc": "5万点赞",
      "corner_mark": 1,
      "bvid": "BV1yM41197EQ",
      "enable_vt": 0,
      "vt_display": ""
    },
    {
      "aid": 364892402,
      "type_id": 21,
      "tname": "日常",
      "pic": "http://i2.hdslb.com/bfs/archive/e7d717de31357e4994557ce40d88a9dd3814afd4.jpg",
      "title": "在英国崩溃吃火锅 聊下我的大学申请",
      "pubdate": 1697886000,
      "ctime": 1697843992,
      "tags": [],
      "duration": 556,
      "author": {
        "mid": 26139491,
        "name": "假美食po主",
        "face": "http://i2.hdslb.com/bfs/face/dd151788db4e32540d5ab59210397a5d1c82e11c.jpg"
      },
      "stat": {
        "aid": 364892402,
        "view": 183902,
        "danmaku": 1565,
        "reply": 950,
        "favorite": 3015,
        "coin": 11304,
        "share": 713,
        "now_rank": 0,
        "his_rank": 0,
        "like": 23015,
        "dislike": 0,
        "vt": 0,
        "vv": 183902
      },
      "hot_desc": "",
      "corner_mark": 0,
      "bvid": "BV1W94y1b7he",
      "enable_vt": 0,
      "vt_display": ""
    },
    {
      "aid": 962445160,
      "type_id": 183,
      "tname": "影视剪辑",
      "pic": "http://i0.hdslb.com/bfs/archive/5a1ab585b5ecf278c4a1d60a586833ea1d5767bc.jpg",
      "title": "“熊出没，但是铁牛牛肉面”",
      "pubdate": 1697852043,
      "ctime": 1697852043,
      "tags": [],
      "duration": 80,
      "author": {
        "mid": 392331008,
        "name": "欧丘",
        "face": "https://i2.hdslb.com/bfs/face/ea511cc1f5688c276131675092cebaca4dc8604d.jpg"
      },
      "stat": {
        "aid": 962445160,
        "view": 575206,
        "danmaku": 262,
        "reply": 502,
        "favorite": 11485,
        "coin": 2345,
        "share": 2837,
        "now_rank": 0,
        "his_rank": 0,
        "like": 65005,
        "dislike": 0,
        "vt": 0,
        "vv": 575206
      },
      "hot_desc": "6万点赞",
      "corner_mark": 1,
      "bvid": "BV1nH4y197aV",
      "enable_vt": 0,
      "vt_display": ""
    },
    {
      "aid": 277402489,
      "type_id": 65,
      "tname": "网络游戏",
      "pic": "http://i2.hdslb.com/bfs/archive/7b5faf01be67324bb94796484d19e9c296c5e4cd.jpg",
      "title": "玩MC碰到的小姑娘攻略我不成就直接给我看了军火展示......",
      "pubdate": 1697814271,
      "ctime": 1697814271,
      "tags": [],
      "duration": 616,
      "author": {
        "mid": 171691903,
        "name": "MOYIN_魔音",
        "face": "https://i1.hdslb.com/bfs/face/11e44708582c9674fdeb2992ec62de9d12b77199.jpg"
      },
      "stat": {
        "aid": 277402489,
        "view": 1095221,
        "danmaku": 4547,
        "reply": 3279,
        "favorite": 37811,
        "coin": 17983,
        "share": 6653,
        "now_rank": 0,
        "his_rank": 20,
        "like": 90751,
        "dislike": 0,
        "vt": 0,
        "vv": 1095221
      },
      "hot_desc": "百万播放",
      "corner_mark": 1,
      "bvid": "BV1Aw411F7p4",
      "enable_vt": 0,
      "vt_display": ""
    },
    {
      "aid": 364885510,
      "type_id": 237,
      "tname": "运动文化",
      "pic": "http://i0.hdslb.com/bfs/archive/1b27f2e6118e5316638e51c0303e69e524a36f49.jpg",
      "title": "古代刀盾能否战胜长枪？游戏电影与现实竟有如此差距！博主亲身测试刀盾破枪",
      "pubdate": 1697855522,
      "ctime": 1697815102,
      "tags": [],
      "duration": 345,
      "author": {
        "mid": 124245685,
        "name": "弓刀手大邦",
        "face": "https://i1.hdslb.com/bfs/face/e0fd65b2638b778e67d1f041a7a87a067d0c6eee.jpg"
      },
      "stat": {
        "aid": 364885510,
        "view": 749543,
        "danmaku": 1497,
        "reply": 1793,
        "favorite": 1610,
        "coin": 914,
        "share": 234,
        "now_rank": 0,
        "his_rank": 0,
        "like": 24056,
        "dislike": 0,
        "vt": 0,
        "vv": 749543
      },
      "hot_desc": "",
      "corner_mark": 0,
      "bvid": "BV1h94y1b7Ce",
      "enable_vt": 0,
      "vt_display": ""
    },
    {
      "aid": 832458192,
      "type_id": 183,
      "tname": "影视剪辑",
      "pic": "http://i1.hdslb.com/bfs/archive/f47298998ce12c31acd28cba91e0ea65366b803a.jpg",
      "title": "他，是你小时候幻想的自己吗？ 原来我是绝世高人",
      "pubdate": 1697811157,
      "ctime": 1697811157,
      "tags": [],
      "duration": 1549,
      "author": {
        "mid": 352400497,
        "name": "小杨爱看剧668",
        "face": "https://i1.hdslb.com/bfs/face/4edd4ef75c1ba9e447f7f0c07b6b89d270cbd817.jpg"
      },
      "stat": {
        "aid": 832458192,
        "view": 313921,
        "danmaku": 858,
        "reply": 545,
        "favorite": 2466,
        "coin": 2829,
        "share": 651,
        "now_rank": 0,
        "his_rank": 0,
        "like": 12101,
        "dislike": 0,
        "vt": 0,
        "vv": 313921
      },
      "hot_desc": "",
      "corner_mark": 0,
      "bvid": "BV1o34y1M71T",
      "enable_vt": 0,
      "vt_display": ""
    },
    {
      "aid": 577424848,
      "type_id": 220,
      "tname": "动物二创",
      "pic": "http://i1.hdslb.com/bfs/archive/453f4e08f0149d62e4513ae30ea661d28b8ed9d0.jpg",
      "title": "脑浆都撞匀了",
      "pubdate": 1697798176,
      "ctime": 1697798176,
      "tags": [],
      "duration": 153,
      "author": {
        "mid": 496783876,
        "name": "幸运猎手",
        "face": "https://i1.hdslb.com/bfs/face/3d935e9ad166e858a97dd8077e77107be3d85a84.jpg"
      },
      "stat": {
        "aid": 577424848,
        "view": 1585729,
        "danmaku": 1316,
        "reply": 1808,
        "favorite": 16570,
        "coin": 5845,
        "share": 3956,
        "now_rank": 0,
        "his_rank": 51,
        "like": 102126,
        "dislike": 0,
        "vt": 0,
        "vv": 1585729
      },
      "hot_desc": "百万播放",
      "corner_mark": 1,
      "bvid": "BV1qB4y1o73R",
      "enable_vt": 0,
      "vt_display": ""
    },
    {
      "aid": 959934783,
      "type_id": 137,
      "tname": "明星综合",
      "pic": "http://i2.hdslb.com/bfs/archive/6e85a08a8458311242ca9403c0fd016e2b11e031.jpg",
      "title": "【时代少年团】《三人行》16:头部行",
      "pubdate": 1697882400,
      "ctime": 1697795331,
      "tags": [],
      "duration": 1275,
      "author": {
        "mid": 3670216,
        "name": "TF家族",
        "face": "http://i1.hdslb.com/bfs/face/1c74336b9060d40d0ccf5e8bce7c0de34526b1e3.jpg"
      },
      "stat": {
        "aid": 959934783,
        "view": 312181,
        "danmaku": 15299,
        "reply": 1661,
        "favorite": 3825,
        "coin": 4487,
        "share": 338,
        "now_rank": 0,
        "his_rank": 0,
        "like": 19010,
        "dislike": 0,
        "vt": 0,
        "vv": 312181
      },
      "hot_desc": "",
      "corner_mark": 0,
      "bvid": "BV1Gp4y1M7RQ",
      "enable_vt": 0,
      "vt_display": ""
    },
    {
      "aid": 364982158,
      "type_id": 85,
      "tname": "小剧场",
      "pic": "http://i1.hdslb.com/bfs/archive/d71cd7d2194a3c2a43d7d00246249d6ad540661b.jpg",
      "title": "参观啦！",
      "pubdate": 1697881559,
      "ctime": 1697881560,
      "tags": [],
      "duration": 239,
      "author": {
        "mid": 373388923,
        "name": "脱缰凯Kk",
        "face": "https://i1.hdslb.com/bfs/face/1367615bfd41b079eae1ac1225dbefcc260acbbb.jpg"
      },
      "stat": {
        "aid": 364982158,
        "view": 401499,
        "danmaku": 1208,
        "reply": 718,
        "favorite": 3448,
        "coin": 3669,
        "share": 338,
        "now_rank": 0,
        "his_rank": 0,
        "like": 53243,
        "dislike": 0,
        "vt": 0,
        "vv": 401499
      },
      "hot_desc": "5万点赞",
      "corner_mark": 1,
      "bvid": "BV1Y94y1L79H",
      "enable_vt": 0,
      "vt_display": ""
    },
    {
      "aid": 959910529,
      "type_id": 176,
      "tname": "汽车生活",
      "pic": "http://i0.hdslb.com/bfs/archive/45bed48bcac340d3ff3c61a14365c29f99d38ac7.jpg",
      "title": "8年&40万过后。。",
      "pubdate": 1697798582,
      "ctime": 1697798582,
      "tags": [],
      "duration": 154,
      "author": {
        "mid": 15527465,
        "name": "高璇Echo",
        "face": "http://i2.hdslb.com/bfs/face/260fc98de6b3a5091f2a11384d9aa65a9e53fe80.jpg"
      },
      "stat": {
        "aid": 959910529,
        "view": 1029049,
        "danmaku": 716,
        "reply": 896,
        "favorite": 7977,
        "coin": 28364,
        "share": 821,
        "now_rank": 0,
        "his_rank": 44,
        "like": 134454,
        "dislike": 0,
        "vt": 0,
        "vv": 1029049
      },
      "hot_desc": "百万播放",
      "corner_mark": 1,
      "bvid": "BV1Lp4y1M7WM",
      "enable_vt": 0,
      "vt_display": ""
    },
    {
      "aid": 322423732,
      "type_id": 182,
      "tname": "影视杂谈",
      "pic": "http://i0.hdslb.com/bfs/archive/a938ab2950cf364595087d66e1ae591fa196b677.jpg",
      "title": "大战小雷音！佛教内部矛盾重重，弥勒佛为什么不开心？",
      "pubdate": 1697850000,
      "ctime": 1697796126,
      "tags": [],
      "duration": 2942,
      "author": {
        "mid": 8096990,
        "name": "啊粥粥啊粥",
        "face": "https://i2.hdslb.com/bfs/face/79c1cf49166f6354d8814e93a4c8e1b55cfc03f2.jpg"
      },
      "stat": {
        "aid": 322423732,
        "view": 721584,
        "danmaku": 7539,
        "reply": 1628,
        "favorite": 8784,
        "coin": 20159,
        "share": 1640,
        "now_rank": 0,
        "his_rank": 0,
        "like": 43823,
        "dislike": 0,
        "vt": 0,
        "vv": 721584
      },
      "hot_desc": "",
      "corner_mark": 0,
      "bvid": "BV1fw41167Dx",
      "enable_vt": 0,
      "vt_display": ""
    },
    {
      "aid": 662426722,
      "type_id": 154,
      "tname": "舞蹈综合",
      "pic": "http://i1.hdslb.com/bfs/archive/79373dc3e8b58038046bfa16623fba813efa2d8c.jpg",
      "title": "坤刀…年轻人的第一套刀法！",
      "pubdate": 1697770800,
      "ctime": 1697758185,
      "tags": [],
      "duration": 74,
      "author": {
        "mid": 27565758,
        "name": "-小D-biu",
        "face": "https://i0.hdslb.com/bfs/face/fe38309daf3e98e51461fb2a0a149732d61437e7.jpg"
      },
      "stat": {
        "aid": 662426722,
        "view": 3721910,
        "danmaku": 4061,
        "reply": 6279,
        "favorite": 60688,
        "coin": 72308,
        "share": 46173,
        "now_rank": 0,
        "his_rank": 1,
        "like": 409026,
        "dislike": 0,
        "vt": 0,
        "vv": 3721910
      },
      "hot_desc": "百万播放",
      "corner_mark": 1,
      "bvid": "BV1sh4y1B72a",
      "enable_vt": 0,
      "vt_display": ""
    },
    {
      "aid": 619921292,
      "type_id": 252,
      "tname": "仿妆cos",
      "pic": "http://i1.hdslb.com/bfs/archive/1942a7896e3a9fe14522d20b107048c0d674bf13.jpg",
      "title": "喜欢珂赛特是你的命运 ❤️",
      "pubdate": 1697869765,
      "ctime": 1697864818,
      "tags": [],
      "duration": 74,
      "author": {
        "mid": 18343098,
        "name": "河野华",
        "face": "https://i0.hdslb.com/bfs/face/d098210fe84dff4d895b60c1b9b99c9b6e22081c.jpg"
      },
      "stat": {
        "aid": 619921292,
        "view": 554512,
        "danmaku": 475,
        "reply": 1537,
        "favorite": 18884,
        "coin": 22499,
        "share": 2762,
        "now_rank": 0,
        "his_rank": 0,
        "like": 84980,
        "dislike": 0,
        "vt": 0,
        "vv": 554512
      },
      "hot_desc": "8万点赞",
      "corner_mark": 1,
      "bvid": "BV1P84y1o7MU",
      "enable_vt": 0,
      "vt_display": ""
    },
    {
      "aid": 704721404,
      "type_id": 183,
      "tname": "影视剪辑",
      "pic": "http://i1.hdslb.com/bfs/archive/afcd019c065492c9b9f374845265000a5e6d5778.jpg",
      "title": "“我们生来普通，但也生来伟大”",
      "pubdate": 1697353858,
      "ctime": 1697353432,
      "tags": [],
      "duration": 189,
      "author": {
        "mid": 1712646894,
        "name": "和风up",
        "face": "https://i0.hdslb.com/bfs/face/68faaa14b191a4797f5f5d9ee12b2e16af98c498.jpg"
      },
      "stat": {
        "aid": 704721404,
        "view": 4144663,
        "danmaku": 841,
        "reply": 1770,
        "favorite": 96599,
        "coin": 40882,
        "share": 3020,
        "now_rank": 0,
        "his_rank": 4,
        "like": 447994,
        "dislike": 0,
        "vt": 0,
        "vv": 4144663
      },
      "hot_desc": "百万播放",
      "corner_mark": 1,
      "bvid": "BV1KQ4y1s71W",
      "enable_vt": 0,
      "vt_display": ""
    },
    {
      "aid": 277443926,
      "type_id": 212,
      "tname": "美食侦探",
      "pic": "http://i1.hdslb.com/bfs/archive/3df9b5b458bcc8466afe969a2644b00d3a4f767d.jpg",
      "title": "探秘全球最豪华头等舱！10万一张机票！飞机餐都吃什么？",
      "pubdate": 1697882400,
      "ctime": 1697832573,
      "tags": [],
      "duration": 485,
      "author": {
        "mid": 406636263,
        "name": "HOLA小测佬",
        "face": "https://i0.hdslb.com/bfs/face/8d076e9dffc6457c18d050b20195aba05c9996ea.jpg"
      },
      "stat": {
        "aid": 277443926,
        "view": 201312,
        "danmaku": 3004,
        "reply": 460,
        "favorite": 3289,
        "coin": 10585,
        "share": 1000,
        "now_rank": 0,
        "his_rank": 0,
        "like": 29750,
        "dislike": 0,
        "vt": 0,
        "vv": 201312
      },
      "hot_desc": "",
      "corner_mark": 0,
      "bvid": "BV1Lw411F7NU",
      "enable_vt": 0,
      "vt_display": ""
    },
    {
      "aid": 534996348,
      "type_id": 241,
      "tname": "娱乐杂谈",
      "pic": "http://i0.hdslb.com/bfs/archive/5b5a48ae501334c09512d2a761358721a204c9f9.jpg",
      "title": "网红之间亦有差距？怪鸽亲手放弃了泼天的富贵！",
      "pubdate": 1697792400,
      "ctime": 1697767773,
      "tags": [],
      "duration": 141,
      "author": {
        "mid": 677139412,
        "name": "咕噜一口小三胖",
        "face": "https://i1.hdslb.com/bfs/face/136b571702d2be06e8206c00068b2fbb61f98bd5.jpg"
      },
      "stat": {
        "aid": 534996348,
        "view": 1903569,
        "danmaku": 1474,
        "reply": 2724,
        "favorite": 23797,
        "coin": 16201,
        "share": 1579,
        "now_rank": 0,
        "his_rank": 6,
        "like": 270849,
        "dislike": 0,
        "vt": 0,
        "vv": 1903569
      },
      "hot_desc": "百万播放",
      "corner_mark": 1,
      "bvid": "BV1jM411R7X7",
      "enable_vt": 0,
      "vt_display": ""
    },
    {
      "aid": 874842681,
      "type_id": 183,
      "tname": "影视剪辑",
      "pic": "http://i0.hdslb.com/bfs/archive/93eea3f0ed895aa5668eaf2f029b8ceea84cedf3.jpg",
      "title": "真的，每一帧都是热爱",
      "pubdate": 1697623521,
      "ctime": 1697623521,
      "tags": [],
      "duration": 138,
      "author": {
        "mid": 314830550,
        "name": "三拾视频",
        "face": "https://i2.hdslb.com/bfs/face/c85d1084d948e397244de8a2d2a4c7dc004246c9.jpg"
      },
      "stat": {
        "aid": 874842681,
        "view": 1445461,
        "danmaku": 985,
        "reply": 718,
        "favorite": 39897,
        "coin": 109033,
        "share": 1761,
        "now_rank": 0,
        "his_rank": 3,
        "like": 296257,
        "dislike": 0,
        "vt": 0,
        "vv": 1445461
      },
      "hot_desc": "百万播放",
      "corner_mark": 1,
      "bvid": "BV1EN4y1C7DF",
      "enable_vt": 0,
      "vt_display": ""
    },
    {
      "aid": 319862086,
      "type_id": 124,
      "tname": "社科·法律·心理",
      "pic": "http://i2.hdslb.com/bfs/archive/0615a02c63a98ef7ce1132f26a942bb166810aa5.jpg",
      "title": "老爷爷对抗全小区20年，只为守护满屋垃圾和蟑螂！最后全被我们扔了",
      "pubdate": 1697631608,
      "ctime": 1697629380,
      "tags": [],
      "duration": 947,
      "author": {
        "mid": 11097284,
        "name": "康哟喂",
        "face": "https://i2.hdslb.com/bfs/face/1083606d23161d330065988fa26d22873df60f25.jpg"
      },
      "stat": {
        "aid": 319862086,
        "view": 2824106,
        "danmaku": 12845,
        "reply": 4175,
        "favorite": 28765,
        "coin": 69190,
        "share": 14227,
        "now_rank": 0,
        "his_rank": 5,
        "like": 167218,
        "dislike": 0,
        "vt": 0,
        "vv": 2824106
      },
      "hot_desc": "百万播放",
      "corner_mark": 1,
      "bvid": "BV1Vw411X7xT",
      "enable_vt": 0,
      "vt_display": ""
    },
    {
      "aid": 492448930,
      "type_id": 138,
      "tname": "搞笑",
      "pic": "http://i1.hdslb.com/bfs/archive/3530445f9ca565eda6be4bc0e8bb02fb595c11e3.jpg",
      "title": "整蛊！偷偷挖空床垫藏在里面...在女友上床时一把抱住她？她懵了！",
      "pubdate": 1697885391,
      "ctime": 1697885198,
      "tags": [],
      "duration": 606,
      "author": {
        "mid": 285571498,
        "name": "盖里老哥",
        "face": "https://i1.hdslb.com/bfs/face/72316bb2a722e7e69c8762958a272af63717182f.jpg"
      },
      "stat": {
        "aid": 492448930,
        "view": 165797,
        "danmaku": 786,
        "reply": 428,
        "favorite": 1321,
        "coin": 4121,
        "share": 391,
        "now_rank": 0,
        "his_rank": 0,
        "like": 17337,
        "dislike": 0,
        "vt": 0,
        "vv": 165797
      },
      "hot_desc": "很多人点赞",
      "corner_mark": 1,
      "bvid": "BV1bN411x7qk",
      "enable_vt": 0,
      "vt_display": ""
    },
    {
      "aid": 959917473,
      "type_id": 158,
      "tname": "穿搭",
      "pic": "http://i1.hdslb.com/bfs/archive/5fd142d0e07816268f80b0d3f6f4bed68c4a2954.jpg",
      "title": "如何穿长裙转圈像公主而不是主公",
      "pubdate": 1697854162,
      "ctime": 1697854162,
      "tags": [],
      "duration": 270,
      "author": {
        "mid": 3529924,
        "name": "幼儿园园长老凛",
        "face": "https://i1.hdslb.com/bfs/face/b0ae0af17676d4caaf2101e505d6098eea0e159a.jpg"
      },
      "stat": {
        "aid": 959917473,
        "view": 322689,
        "danmaku": 315,
        "reply": 482,
        "favorite": 9658,
        "coin": 1738,
        "share": 1792,
        "now_rank": 0,
        "his_rank": 0,
        "like": 38188,
        "dislike": 0,
        "vt": 0,
        "vv": 322689
      },
      "hot_desc": "",
      "corner_mark": 0,
      "bvid": "BV1Lp4y1M7qd",
      "enable_vt": 0,
      "vt_display": ""
    },
    {
      "aid": 789944246,
      "type_id": 247,
      "tname": "新能源车",
      "pic": "http://i0.hdslb.com/bfs/archive/d562d55b7d3b44c6cabca23ab40df8c771c6f52d.jpg",
      "title": "5年爆赚3000亿？沃尔沃100年史上销量第二车！15年狂销225万辆的XC60，竟是精准定位的夫妻带娃车？【镖车·沃尔沃XC60】",
      "pubdate": 1697857200,
      "ctime": 1697807053,
      "tags": [],
      "duration": 694,
      "author": {
        "mid": 1575718735,
        "name": "保镖的车库",
        "face": "https://i1.hdslb.com/bfs/face/a9a7b7acde65a4aa7eb23c601a90b636a7f47117.jpg"
      },
      "stat": {
        "aid": 789944246,
        "view": 263786,
        "danmaku": 773,
        "reply": 599,
        "favorite": 1575,
        "coin": 1335,
        "share": 674,
        "now_rank": 0,
        "his_rank": 0,
        "like": 15968,
        "dislike": 0,
        "vt": 0,
        "vv": 263786
      },
      "hot_desc": "",
      "corner_mark": 0,
      "bvid": "BV1Jy4y1P77o",
      "enable_vt": 0,
      "vt_display": ""
    },
    {
      "aid": 959977836,
      "type_id": 95,
      "tname": "数码",
      "pic": "http://i2.hdslb.com/bfs/archive/3bb33ddd9529de77fff9539915bb87b949fdecfe.jpg",
      "title": "仅售32元的儿童手机不能上网？没关系，我会出手！",
      "pubdate": 1697855065,
      "ctime": 1697855066,
      "tags": [],
      "duration": 419,
      "author": {
        "mid": 251013709,
        "name": "晨钟酱Official",
        "face": "https://i1.hdslb.com/bfs/face/dcbe22562ca561a4e2423d7dceb6ed8a3752a5cb.jpg"
      },
      "stat": {
        "aid": 959977836,
        "view": 475485,
        "danmaku": 848,
        "reply": 1091,
        "favorite": 6454,
        "coin": 3267,
        "share": 465,
        "now_rank": 0,
        "his_rank": 0,
        "like": 28752,
        "dislike": 0,
        "vt": 0,
        "vv": 475485
      },
      "hot_desc": "",
      "corner_mark": 0,
      "bvid": "BV19p4y1N7H8",
      "enable_vt": 0,
      "vt_display": ""
    },
    {
      "aid": 832394225,
      "type_id": 47,
      "tname": "短片·手书",
      "pic": "http://i0.hdslb.com/bfs/archive/10d5d8ccb39558afe8d6a0576d6710d9f9a8ad81.jpg",
      "title": "当 代 热 门 软 件 现 状",
      "pubdate": 1697797375,
      "ctime": 1697797375,
      "tags": [],
      "duration": 113,
      "author": {
        "mid": 321422126,
        "name": "进击的金厂长",
        "face": "https://i2.hdslb.com/bfs/face/a34eddc74f7bffb96f77b37b4f27b793d892863b.jpg"
      },
      "stat": {
        "aid": 832394225,
        "view": 1213475,
        "danmaku": 743,
        "reply": 506,
        "favorite": 10572,
        "coin": 42892,
        "share": 892,
        "now_rank": 0,
        "his_rank": 0,
        "like": 124833,
        "dislike": 0,
        "vt": 0,
        "vv": 1213475
      },
      "hot_desc": "百万播放",
      "corner_mark": 1,
      "bvid": "BV1z34y1M7eM",
      "enable_vt": 0,
      "vt_display": ""
    },
    {
      "aid": 619923832,
      "type_id": 250,
      "tname": "出行",
      "pic": "http://i1.hdslb.com/bfs/archive/4542cce773e7be71d145e2bc269be136f49efa66.jpg",
      "title": "恐怖主题酒店！在棺材上睡一晚是什么体验？",
      "pubdate": 1697860800,
      "ctime": 1697825067,
      "tags": [],
      "duration": 489,
      "author": {
        "mid": 285499073,
        "name": "东尼ookii",
        "face": "https://i2.hdslb.com/bfs/face/456b2bff7e41ab212b74e9019fda1f26362e8723.jpg"
      },
      "stat": {
        "aid": 619923832,
        "view": 524395,
        "danmaku": 3233,
        "reply": 1258,
        "favorite": 4204,
        "coin": 6693,
        "share": 9637,
        "now_rank": 0,
        "his_rank": 0,
        "like": 40825,
        "dislike": 0,
        "vt": 0,
        "vv": 524395
      },
      "hot_desc": "",
      "corner_mark": 0,
      "bvid": "BV1R84y1d7mi",
      "enable_vt": 0,
      "vt_display": ""
    },
    {
      "aid": 492298460,
      "type_id": 17,
      "tname": "单机游戏",
      "pic": "http://i1.hdslb.com/bfs/archive/5dfce13acb3dd54e6cd812f3ff3cc61036477379.jpg",
      "title": "疾 速 追 杀 × 无 暇 赴 死",
      "pubdate": 1697770852,
      "ctime": 1697725221,
      "tags": [],
      "duration": 100,
      "author": {
        "mid": 27693245,
        "name": "灰雾絮雨",
        "face": "https://i2.hdslb.com/bfs/face/1ae37c7e1e5e6291279caf4a12214a23ac0d9109.jpg"
      },
      "stat": {
        "aid": 492298460,
        "view": 837404,
        "danmaku": 634,
        "reply": 803,
        "favorite": 22700,
        "coin": 4222,
        "share": 2081,
        "now_rank": 0,
        "his_rank": 0,
        "like": 83507,
        "dislike": 0,
        "vt": 0,
        "vv": 837404
      },
      "hot_desc": "8万点赞",
      "corner_mark": 1,
      "bvid": "BV1LN411t72D",
      "enable_vt": 0,
      "vt_display": ""
    },
    {
      "aid": 322406614,
      "type_id": 27,
      "tname": "综合",
      "pic": "http://i1.hdslb.com/bfs/archive/3de87907f545b962e3306607821268a21918fd86.jpg",
      "title": "双向奔赴的爱情才有意义！",
      "pubdate": 1697787748,
      "ctime": 1697787748,
      "tags": [],
      "duration": 105,
      "author": {
        "mid": 1056251876,
        "name": "超燃漫酱",
        "face": "https://i2.hdslb.com/bfs/face/b01c21bb586c8527819b4a46f2397a456f02a516.jpg"
      },
      "stat": {
        "aid": 322406614,
        "view": 202793,
        "danmaku": 367,
        "reply": 346,
        "favorite": 3512,
        "coin": 3729,
        "share": 302,
        "now_rank": 0,
        "his_rank": 0,
        "like": 22191,
        "dislike": 0,
        "vt": 0,
        "vv": 202793
      },
      "hot_desc": "动画综合·人气飙升",
      "corner_mark": 1,
      "bvid": "BV1Pw411r74f",
      "enable_vt": 0,
      "vt_display": ""
    },
    {
      "aid": 319921764,
      "type_id": 172,
      "tname": "手机游戏",
      "pic": "http://i0.hdslb.com/bfs/archive/e5f35b19fcd0748dd5c44f039a5b0f3dcaf977f5.jpg",
      "title": "《无期迷途》限时活动——「噩玩惊魂」",
      "pubdate": 1697860800,
      "ctime": 1697802360,
      "tags": [],
      "duration": 131,
      "author": {
        "mid": 647409444,
        "name": "无期迷途",
        "face": "https://i0.hdslb.com/bfs/face/92023349e9b3dad2baad0412411b86acfec883f8.jpg"
      },
      "stat": {
        "aid": 319921764,
        "view": 537606,
        "danmaku": 1425,
        "reply": 2661,
        "favorite": 3267,
        "coin": 6599,
        "share": 5515,
        "now_rank": 0,
        "his_rank": 0,
        "like": 26712,
        "dislike": 0,
        "vt": 0,
        "vv": 537606
      },
      "hot_desc": "",
      "corner_mark": 0,
      "bvid": "BV18w411X7o8",
      "enable_vt": 0,
      "vt_display": ""
    },
    {
      "aid": 789894118,
      "type_id": 17,
      "tname": "单机游戏",
      "pic": "http://i0.hdslb.com/bfs/archive/2c75700ea9e4f636149a6186fc014028a317fa38.jpg",
      "title": "\"她造了1000个房间，来收容怪物！\"",
      "pubdate": 1697794200,
      "ctime": 1697766830,
      "tags": [],
      "duration": 820,
      "author": {
        "mid": 10874201,
        "name": "盒子酸奶",
        "face": "https://i2.hdslb.com/bfs/face/eeb7692fe046da4b9bc88788af68c243ed585546.jpg"
      },
      "stat": {
        "aid": 789894118,
        "view": 1869861,
        "danmaku": 3063,
        "reply": 735,
        "favorite": 55217,
        "coin": 11334,
        "share": 1233,
        "now_rank": 0,
        "his_rank": 10,
        "like": 130599,
        "dislike": 0,
        "vt": 0,
        "vv": 1869861
      },
      "hot_desc": "百万播放",
      "corner_mark": 1,
      "bvid": "BV1Ry4y1A75H",
      "enable_vt": 0,
      "vt_display": ""
    },
    {
      "aid": 577456582,
      "type_id": 124,
      "tname": "社科·法律·心理",
      "pic": "http://i2.hdslb.com/bfs/archive/6972a221bc60a4b202386f080e3afeb4a955e8c3.jpg",
      "title": "女环卫工被两男子暴打后，我做了一个2万字环卫生存状态调研！【看见平凡系列06】",
      "pubdate": 1697794470,
      "ctime": 1697794470,
      "tags": [],
      "duration": 1473,
      "author": {
        "mid": 680677803,
        "name": "王小七Fire",
        "face": "https://i0.hdslb.com/bfs/face/900ca78e5515ba71e200eaaf83f579004243ca63.jpg"
      },
      "stat": {
        "aid": 577456582,
        "view": 1073281,
        "danmaku": 2894,
        "reply": 3757,
        "favorite": 16539,
        "coin": 47100,
        "share": 2224,
        "now_rank": 0,
        "his_rank": 13,
        "like": 136222,
        "dislike": 0,
        "vt": 0,
        "vv": 1073281
      },
      "hot_desc": "百万播放",
      "corner_mark": 1,
      "bvid": "BV1mB4y1o75D",
      "enable_vt": 0,
      "vt_display": ""
    },
    {
      "aid": 277310421,
      "type_id": 207,
      "tname": "财经商业",
      "pic": "http://i0.hdslb.com/bfs/archive/548b79ccf9609ee4c85e15425d3a059b16477ce3.jpg",
      "title": "【半佛】李子园称霸早餐摊，全靠省钱的艺术。",
      "pubdate": 1697709311,
      "ctime": 1697709311,
      "tags": [],
      "duration": 405,
      "author": {
        "mid": 37663924,
        "name": "硬核的半佛仙人",
        "face": "https://i1.hdslb.com/bfs/face/aaf33dced1941af0946f37c62f4b48fcaba9c9a2.jpg"
      },
      "stat": {
        "aid": 277310421,
        "view": 989898,
        "danmaku": 1623,
        "reply": 2870,
        "favorite": 3919,
        "coin": 1859,
        "share": 1460,
        "now_rank": 0,
        "his_rank": 0,
        "like": 49296,
        "dislike": 0,
        "vt": 0,
        "vv": 989898
      },
      "hot_desc": "",
      "corner_mark": 0,
      "bvid": "BV15w411w7e1",
      "enable_vt": 0,
      "vt_display": ""
    },
    {
      "aid": 874984973,
      "type_id": 215,
      "tname": "美食记录",
      "pic": "http://i1.hdslb.com/bfs/archive/c53e4c4bdc7ee55da82b97620bf54c51833e31d9.jpg",
      "title": "老王画缘：烤鱼",
      "pubdate": 1697793032,
      "ctime": 1697793032,
      "tags": [],
      "duration": 207,
      "author": {
        "mid": 3546556351384136,
        "name": "老王日记油画",
        "face": "https://i2.hdslb.com/bfs/face/30bd786179f7d0fb3adc18b2ce47c84af4f4dec2.jpg"
      },
      "stat": {
        "aid": 874984973,
        "view": 808285,
        "danmaku": 1763,
        "reply": 1323,
        "favorite": 4923,
        "coin": 7162,
        "share": 662,
        "now_rank": 0,
        "his_rank": 57,
        "like": 136279,
        "dislike": 0,
        "vt": 0,
        "vv": 808285
      },
      "hot_desc": "13万点赞",
      "corner_mark": 1,
      "bvid": "BV1AN4y1y71g",
      "enable_vt": 0,
      "vt_display": ""
    },
    {
      "aid": 917489004,
      "type_id": 161,
      "tname": "手工",
      "pic": "http://i0.hdslb.com/bfs/archive/7b047bfb5cdcb51c1a57aee8082b61ab53dca581.jpg",
      "title": "死磕到底！终于把大哥定制的刀做出来了，江湖上又要掀起怎样的血雨腥风？",
      "pubdate": 1697817456,
      "ctime": 1697817456,
      "tags": [],
      "duration": 193,
      "author": {
        "mid": 104381123,
        "name": "昭铭天声",
        "face": "https://i2.hdslb.com/bfs/face/8a78528ed9456c5f93e4d1a139144654e461400b.jpg"
      },
      "stat": {
        "aid": 917489004,
        "view": 898330,
        "danmaku": 507,
        "reply": 1078,
        "favorite": 2677,
        "coin": 1695,
        "share": 330,
        "now_rank": 0,
        "his_rank": 0,
        "like": 57928,
        "dislike": 0,
        "vt": 0,
        "vv": 898330
      },
      "hot_desc": "",
      "corner_mark": 0,
      "bvid": "BV1Hu4y1W75L",
      "enable_vt": 0,
      "vt_display": ""
    },
    {
      "aid": 364972722,
      "type_id": 241,
      "tname": "娱乐杂谈",
      "pic": "http://i1.hdslb.com/bfs/archive/714a25f4b1ff32326bbd96558cbe832cf6d8920d.jpg",
      "title": "兄弟激情开麦，猛料爆梗狂放，热搜彻底失控【陈牧驰吴楚一细节全盘点】",
      "pubdate": 1697858040,
      "ctime": 1697858040,
      "tags": [],
      "duration": 1174,
      "author": {
        "mid": 20457232,
        "name": "一只吐槽圆",
        "face": "https://i1.hdslb.com/bfs/face/bc2f05efa553aa28def1cc1198bb7920993730bd.jpg"
      },
      "stat": {
        "aid": 364972722,
        "view": 533035,
        "danmaku": 6830,
        "reply": 3097,
        "favorite": 3957,
        "coin": 3949,
        "share": 13036,
        "now_rank": 0,
        "his_rank": 0,
        "like": 30788,
        "dislike": 0,
        "vt": 0,
        "vv": 533035
      },
      "hot_desc": "1万分享",
      "corner_mark": 1,
      "bvid": "BV1h94y1L7rk",
      "enable_vt": 0,
      "vt_display": ""
    },
    {
      "aid": 917270355,
      "type_id": 138,
      "tname": "搞笑",
      "pic": "http://i0.hdslb.com/bfs/archive/d0fb6f08189b5937db72e73abccc03262b8373db.jpg",
      "title": "假如没有禁毒，世界会怎么样？海南警方最新禁毒宣传片！",
      "pubdate": 1697778000,
      "ctime": 1697720704,
      "tags": [],
      "duration": 77,
      "author": {
        "mid": 409973974,
        "name": "蜀黍举个栗子",
        "face": "https://i1.hdslb.com/bfs/face/a74a70540c9e55919f4578e756b1590faf08cb7e.jpg"
      },
      "stat": {
        "aid": 917270355,
        "view": 1373842,
        "danmaku": 220,
        "reply": 1021,
        "favorite": 9069,
        "coin": 9631,
        "share": 481,
        "now_rank": 0,
        "his_rank": 61,
        "like": 185801,
        "dislike": 0,
        "vt": 0,
        "vv": 1373842
      },
      "hot_desc": "百万播放",
      "corner_mark": 1,
      "bvid": "BV1Vu4y1p7c4",
      "enable_vt": 0,
      "vt_display": ""
    },
    {
      "aid": 577419148,
      "type_id": 228,
      "tname": "人文历史",
      "pic": "http://i0.hdslb.com/bfs/archive/67ae362a9127947617257cd98fa2cee77a4fe92f.jpg",
      "title": "日本无敌软饭男，被7任女友包养13年，出书总结吃软饭秘诀",
      "pubdate": 1697803457,
      "ctime": 1697803457,
      "tags": [],
      "duration": 481,
      "author": {
        "mid": 1858520088,
        "name": "见世君",
        "face": "https://i0.hdslb.com/bfs/face/9fe9d1f9782b9aab574128e97deb387a6e5215d5.jpg"
      },
      "stat": {
        "aid": 577419148,
        "view": 1271518,
        "danmaku": 5754,
        "reply": 6212,
        "favorite": 16986,
        "coin": 4315,
        "share": 21867,
        "now_rank": 0,
        "his_rank": 90,
        "like": 43723,
        "dislike": 0,
        "vt": 0,
        "vv": 1271518
      },
      "hot_desc": "百万播放",
      "corner_mark": 1,
      "bvid": "BV12B4y1o78k",
      "enable_vt": 0,
      "vt_display": ""
    },
    {
      "aid": 959839474,
      "type_id": 213,
      "tname": "美食测评",
      "pic": "http://i1.hdslb.com/bfs/archive/a9699d9cf2b73a59dbce1e423dacdb988354ab03.jpg",
      "title": "笑拥了！带货主播推荐的“迷惑水果”太离谱了吧？！",
      "pubdate": 1697791800,
      "ctime": 1697729455,
      "tags": [],
      "duration": 780,
      "author": {
        "mid": 478691043,
        "name": "穿毛裤的小拉泽",
        "face": "https://i0.hdslb.com/bfs/face/023c69a89a95db1b7991a024c0806d2ed7e58021.jpg"
      },
      "stat": {
        "aid": 959839474,
        "view": 1106988,
        "danmaku": 13456,
        "reply": 1546,
        "favorite": 6868,
        "coin": 19631,
        "share": 771,
        "now_rank": 0,
        "his_rank": 76,
        "like": 83174,
        "dislike": 0,
        "vt": 0,
        "vv": 1106988
      },
      "hot_desc": "8万点赞",
      "corner_mark": 1,
      "bvid": "BV1rp4y1T7zH",
      "enable_vt": 0,
      "vt_display": ""
    },
    {
      "aid": 534913768,
      "type_id": 216,
      "tname": "鬼畜剧场",
      "pic": "http://i0.hdslb.com/bfs/archive/532bc2739f700444db74af4b178ba38bbd5dd336.jpg",
      "title": "【特效大作向】蔡徐坤vs全明星（28分钟完整版）",
      "pubdate": 1697885071,
      "ctime": 1697885072,
      "tags": [],
      "duration": 1680,
      "author": {
        "mid": 22770727,
        "name": "豪言の经理",
        "face": "https://i1.hdslb.com/bfs/face/56ec3c5f0a34b8d8f79c6b004f556f5993641fd4.jpg"
      },
      "stat": {
        "aid": 534913768,
        "view": 72121,
        "danmaku": 1071,
        "reply": 530,
        "favorite": 3090,
        "coin": 5114,
        "share": 686,
        "now_rank": 0,
        "his_rank": 0,
        "like": 13665,
        "dislike": 0,
        "vt": 0,
        "vv": 72121
      },
      "hot_desc": "",
      "corner_mark": 0,
      "bvid": "BV1wM411R7iR",
      "enable_vt": 0,
      "vt_display": ""
    },
    {
      "aid": 704895131,
      "type_id": 220,
      "tname": "动物二创",
      "pic": "http://i2.hdslb.com/bfs/archive/3146e3a93980af1e2e602fe3e72b938f09587daf.jpg",
      "title": "哥哥！请不要过度高冷！",
      "pubdate": 1697806109,
      "ctime": 1697806109,
      "tags": [],
      "duration": 124,
      "author": {
        "mid": 1893045,
        "name": "狂风桑",
        "face": "https://i0.hdslb.com/bfs/face/5076846bb07c2d6ec442856f69214cae215301f3.jpg"
      },
      "stat": {
        "aid": 704895131,
        "view": 642616,
        "danmaku": 321,
        "reply": 561,
        "favorite": 7803,
        "coin": 5593,
        "share": 10247,
        "now_rank": 0,
        "his_rank": 0,
        "like": 58613,
        "dislike": 0,
        "vt": 0,
        "vv": 642616
      },
      "hot_desc": "5万点赞",
      "corner_mark": 1,
      "bvid": "BV1UQ4y1s7bG",
      "enable_vt": 0,
      "vt_display": ""
    },
    {
      "aid": 234973555,
      "type_id": 212,
      "tname": "美食侦探",
      "pic": "http://i0.hdslb.com/bfs/archive/148ffb90cf830e0097bbff3df35088d62789415a.jpg",
      "title": "江南早市？碳水天堂！南方街头豪橫早餐，焦酥外壳汁水四溢",
      "pubdate": 1697796000,
      "ctime": 1697791072,
      "tags": [],
      "duration": 1486,
      "author": {
        "mid": 39627524,
        "name": "食贫道",
        "face": "https://i2.hdslb.com/bfs/face/eef12b850c10b0d7a7929236abb08604955823c0.jpg"
      },
      "stat": {
        "aid": 234973555,
        "view": 653503,
        "danmaku": 7113,
        "reply": 1407,
        "favorite": 12320,
        "coin": 48286,
        "share": 4985,
        "now_rank": 0,
        "his_rank": 37,
        "like": 102104,
        "dislike": 0,
        "vt": 0,
        "vv": 653503
      },
      "hot_desc": "10万点赞",
      "corner_mark": 1,
      "bvid": "BV1Be411R7fQ",
      "enable_vt": 0,
      "vt_display": ""
    },
    {
      "aid": 662273291,
      "type_id": 17,
      "tname": "单机游戏",
      "pic": "http://i1.hdslb.com/bfs/archive/c165d93c24a67fcef7d83ee1ce9e9e705a928a08.png",
      "title": "什么大不大的！我只想给孩子一个家！持续更新3p【完蛋！我被美女包围了！】",
      "pubdate": 1697714042,
      "ctime": 1697714042,
      "tags": [],
      "duration": 5246,
      "author": {
        "mid": 2206456,
        "name": "花少北丶",
        "face": "https://i1.hdslb.com/bfs/face/06c233a0136f738f8f54a08770dc7d484ae45081.jpg"
      },
      "stat": {
        "aid": 662273291,
        "view": 963339,
        "danmaku": 13331,
        "reply": 1909,
        "favorite": 14379,
        "coin": 19054,
        "share": 5100,
        "now_rank": 0,
        "his_rank": 86,
        "like": 51364,
        "dislike": 0,
        "vt": 0,
        "vv": 963339
      },
      "hot_desc": "5万点赞",
      "corner_mark": 1,
      "bvid": "BV1ih4y1q7f4",
      "enable_vt": 0,
      "vt_display": ""
    },
    {
      "aid": 234930525,
      "type_id": 212,
      "tname": "美食侦探",
      "pic": "http://i0.hdslb.com/bfs/archive/e6edee12f37160d29ccc80e49e492971cbcb612b.jpg",
      "title": "粥饼伦的黑色灌饼吃上了 长得确实挺像",
      "pubdate": 1697798063,
      "ctime": 1697798064,
      "tags": [],
      "duration": 53,
      "author": {
        "mid": 1479620036,
        "name": "小曹和辉哥-逛吃",
        "face": "https://i2.hdslb.com/bfs/face/255515de5dbb541dd299f1bbfedf4f9b421d602d.jpg"
      },
      "stat": {
        "aid": 234930525,
        "view": 1993612,
        "danmaku": 400,
        "reply": 984,
        "favorite": 4464,
        "coin": 632,
        "share": 2752,
        "now_rank": 0,
        "his_rank": 0,
        "like": 107941,
        "dislike": 0,
        "vt": 0,
        "vv": 1993612
      },
      "hot_desc": "",
      "corner_mark": 0,
      "bvid": "BV14e411R7sp",
      "enable_vt": 0,
      "vt_display": ""
    },
    {
      "aid": 832482422,
      "type_id": 17,
      "tname": "单机游戏",
      "pic": "http://i1.hdslb.com/bfs/archive/6bce9a96ecbc4a3e9d27221d695582bd3936146d.jpg",
      "title": "主角把人做成装备？这款23年难到变态的游戏还有隐藏结局！",
      "pubdate": 1697792452,
      "ctime": 1697792452,
      "tags": [],
      "duration": 701,
      "author": {
        "mid": 2314623,
        "name": "超级funky橙子",
        "face": "https://i0.hdslb.com/bfs/face/ebeb233a207f24690e3fe77b845dfe29c05a8b5d.jpg"
      },
      "stat": {
        "aid": 832482422,
        "view": 827038,
        "danmaku": 1007,
        "reply": 454,
        "favorite": 17507,
        "coin": 28066,
        "share": 472,
        "now_rank": 0,
        "his_rank": 52,
        "like": 74401,
        "dislike": 0,
        "vt": 0,
        "vv": 827038
      },
      "hot_desc": "7万点赞",
      "corner_mark": 1,
      "bvid": "BV1534y1u723",
      "enable_vt": 0,
      "vt_display": ""
    },
    {
      "aid": 277129517,
      "type_id": 20,
      "tname": "宅舞",
      "pic": "http://i1.hdslb.com/bfs/archive/aef99f572caff4b5a6511a5ef0304cbcfcb44e8b.jpg",
      "title": "おちゃめ機能",
      "pubdate": 1697454828,
      "ctime": 1697454828,
      "tags": [],
      "duration": 102,
      "author": {
        "mid": 1540733893,
        "name": "IReneちゃん",
        "face": "https://i1.hdslb.com/bfs/face/600582c612f23814d99318a8a70d8583793ffb90.jpg"
      },
      "stat": {
        "aid": 277129517,
        "view": 1559211,
        "danmaku": 789,
        "reply": 2709,
        "favorite": 33144,
        "coin": 17257,
        "share": 3829,
        "now_rank": 0,
        "his_rank": 0,
        "like": 111216,
        "dislike": 0,
        "vt": 0,
        "vv": 1559211
      },
      "hot_desc": "百万播放",
      "corner_mark": 1,
      "bvid": "BV1bw411c7zv",
      "enable_vt": 0,
      "vt_display": ""
    },
    {
      "aid": 534888432,
      "type_id": 21,
      "tname": "日常",
      "pic": "http://i1.hdslb.com/bfs/archive/fd441bf111ce04bfdf4679c4dc917b50ca895a48.jpg",
      "title": "女毒贩被抓后闹肚子连声喊冤，被搜出两种毒品后竟还装无辜？",
      "pubdate": 1697790591,
      "ctime": 1697790591,
      "tags": [],
      "duration": 182,
      "author": {
        "mid": 477531206,
        "name": "阿特警官",
        "face": "https://i2.hdslb.com/bfs/face/dae07824002ae3a60f46398888b9679d198e7fc1.jpg"
      },
      "stat": {
        "aid": 534888432,
        "view": 1043526,
        "danmaku": 2877,
        "reply": 2403,
        "favorite": 6000,
        "coin": 2748,
        "share": 1690,
        "now_rank": 0,
        "his_rank": 93,
        "like": 86725,
        "dislike": 0,
        "vt": 0,
        "vv": 1043526
      },
      "hot_desc": "8万点赞",
      "corner_mark": 1,
      "bvid": "BV1XM411975X",
      "enable_vt": 0,
      "vt_display": ""
    },
    {
      "aid": 407407084,
      "type_id": 213,
      "tname": "美食测评",
      "pic": "http://i1.hdslb.com/bfs/archive/e0139f78802adb2458c34591c6f0e29980ee48e1.jpg",
      "title": "挑战全国最便宜自助餐！六元随便吃菜的自助粥真不错啊！",
      "pubdate": 1697857949,
      "ctime": 1697857949,
      "tags": [],
      "duration": 175,
      "author": {
        "mid": 9824766,
        "name": "敬汉卿",
        "face": "https://i0.hdslb.com/bfs/face/fd8d7ad17af295f7c4256959705f009c5f67e9c6.jpg"
      },
      "stat": {
        "aid": 407407084,
        "view": 546161,
        "danmaku": 744,
        "reply": 1462,
        "favorite": 1477,
        "coin": 2368,
        "share": 847,
        "now_rank": 0,
        "his_rank": 0,
        "like": 33261,
        "dislike": 0,
        "vt": 0,
        "vv": 546161
      },
      "hot_desc": "",
      "corner_mark": 0,
      "bvid": "BV1hG411y7wJ",
      "enable_vt": 0,
      "vt_display": ""
    },
    {
      "aid": 322257293,
      "type_id": 21,
      "tname": "日常",
      "pic": "http://i1.hdslb.com/bfs/archive/6663e34f72a8e84f0024a608c1ecaa336b002279.jpg",
      "title": "BGM再一次神卡点",
      "pubdate": 1697557400,
      "ctime": 1697557401,
      "tags": [],
      "duration": 450,
      "author": {
        "mid": 405378715,
        "name": "Alice-然",
        "face": "https://i1.hdslb.com/bfs/face/690b4f9cc421684ff8571477f3ba8b048a88c907.jpg"
      },
      "stat": {
        "aid": 322257293,
        "view": 2784877,
        "danmaku": 5064,
        "reply": 5196,
        "favorite": 40109,
        "coin": 22362,
        "share": 36745,
        "now_rank": 0,
        "his_rank": 1,
        "like": 339799,
        "dislike": 0,
        "vt": 0,
        "vv": 2784877
      },
      "hot_desc": "百万播放",
      "corner_mark": 1,
      "bvid": "BV1uw41167vz",
      "enable_vt": 0,
      "vt_display": ""
    },
    {
      "aid": 319826624,
      "type_id": 171,
      "tname": "电子竞技",
      "pic": "http://i1.hdslb.com/bfs/archive/a39c3196a66566a8f50752eed1d69d2d5029ed30.jpg",
      "title": "《最关爱发育路的一集》",
      "pubdate": 1697796000,
      "ctime": 1697738839,
      "tags": [],
      "duration": 254,
      "author": {
        "mid": 405370021,
        "name": "尴尬的铁根er",
        "face": "https://i1.hdslb.com/bfs/face/cbe228260be3e8d2b49cb2f8dde7a0a41bee1d93.jpg"
      },
      "stat": {
        "aid": 319826624,
        "view": 1635044,
        "danmaku": 1800,
        "reply": 762,
        "favorite": 4224,
        "coin": 2978,
        "share": 486,
        "now_rank": 0,
        "his_rank": 0,
        "like": 84456,
        "dislike": 0,
        "vt": 0,
        "vv": 1635044
      },
      "hot_desc": "",
      "corner_mark": 0,
      "bvid": "BV1ww411X7GA",
      "enable_vt": 0,
      "vt_display": ""
    },
    {
      "aid": 364944168,
      "type_id": 76,
      "tname": "美食制作",
      "pic": "http://i0.hdslb.com/bfs/archive/fe1ea6a20fdbdf6971662478a51e71f64adaa17b.jpg",
      "title": "【密码的馒头】清蒸老虎斑馒头",
      "pubdate": 1697795132,
      "ctime": 1697795132,
      "tags": [],
      "duration": 252,
      "author": {
        "mid": 3493120727583319,
        "name": "Mima-密码",
        "face": "https://i1.hdslb.com/bfs/face/c12fa6590203bcfa9998331257aa177e72309d14.jpg"
      },
      "stat": {
        "aid": 364944168,
        "view": 987055,
        "danmaku": 1516,
        "reply": 1240,
        "favorite": 5615,
        "coin": 21732,
        "share": 6050,
        "now_rank": 0,
        "his_rank": 69,
        "like": 90463,
        "dislike": 0,
        "vt": 0,
        "vv": 987055
      },
      "hot_desc": "8万点赞",
      "corner_mark": 1,
      "bvid": "BV1p94y1L77u",
      "enable_vt": 0,
      "vt_display": ""
    },
    {
      "aid": 492451215,
      "type_id": 253,
      "tname": "动漫杂谈",
      "pic": "http://i1.hdslb.com/bfs/archive/dd48baf0759ba575c7f5bf3d7ca74b5b812671d5.jpg",
      "title": "《普攻永久加生命，阁下如何应对？》每次普攻永久增加一点生命值！普攻造成自身最大生命值1%的真伤！有此天赋，何人能挡！",
      "pubdate": 1697801575,
      "ctime": 1697801575,
      "tags": [],
      "duration": 69776,
      "author": {
        "mid": 670158805,
        "name": "乙坂爱动漫",
        "face": "https://i1.hdslb.com/bfs/face/aeca378efd333163d4674d6fd9e38520a38cecad.jpg"
      },
      "stat": {
        "aid": 492451215,
        "view": 373016,
        "danmaku": 3209,
        "reply": 748,
        "favorite": 14251,
        "coin": 3176,
        "share": 593,
        "now_rank": 0,
        "his_rank": 0,
        "like": 9382,
        "dislike": 0,
        "vt": 0,
        "vv": 373016
      },
      "hot_desc": "",
      "corner_mark": 0,
      "bvid": "BV1hN411x7hs",
      "enable_vt": 0,
      "vt_display": ""
    },
    {
      "aid": 917396586,
      "type_id": 138,
      "tname": "搞笑",
      "pic": "http://i0.hdslb.com/bfs/archive/ecbdbb1d6b7191f1ddb022d3b58cbbab320e1c06.jpg",
      "title": "2023年了，你还敢在外面和人打架吗？？",
      "pubdate": 1697788329,
      "ctime": 1697788330,
      "tags": [],
      "duration": 251,
      "author": {
        "mid": 297242063,
        "name": "黄一刀有毒",
        "face": "https://i2.hdslb.com/bfs/face/cf8480768d0186835523a6d2e5033b12a1006523.jpg"
      },
      "stat": {
        "aid": 917396586,
        "view": 1035651,
        "danmaku": 2505,
        "reply": 4161,
        "favorite": 13735,
        "coin": 8823,
        "share": 5029,
        "now_rank": 0,
        "his_rank": 80,
        "like": 63359,
        "dislike": 0,
        "vt": 0,
        "vv": 1035651
      },
      "hot_desc": "6万点赞",
      "corner_mark": 1,
      "bvid": "BV1Qu4y1p7Yu",
      "enable_vt": 0,
      "vt_display": ""
    },
    {
      "aid": 959849338,
      "type_id": 138,
      "tname": "搞笑",
      "pic": "http://i2.hdslb.com/bfs/archive/da25394b85c1e229c65614b1d5617ae73c7b52c1.jpg",
      "title": "现在的小孩有多难？",
      "pubdate": 1697774400,
      "ctime": 1697731083,
      "tags": [],
      "duration": 340,
      "author": {
        "mid": 95515699,
        "name": "粤知一二",
        "face": "https://i1.hdslb.com/bfs/face/45526a0992aa6cb190863f49be6ac2f49f9bd8d9.jpg"
      },
      "stat": {
        "aid": 959849338,
        "view": 2232636,
        "danmaku": 5052,
        "reply": 2606,
        "favorite": 10749,
        "coin": 2923,
        "share": 2237,
        "now_rank": 0,
        "his_rank": 14,
        "like": 183167,
        "dislike": 0,
        "vt": 0,
        "vv": 2232636
      },
      "hot_desc": "百万播放",
      "corner_mark": 1,
      "bvid": "BV1op4y1T7Vt",
      "enable_vt": 0,
      "vt_display": ""
    },
    {
      "aid": 234996109,
      "type_id": 228,
      "tname": "人文历史",
      "pic": "http://i2.hdslb.com/bfs/archive/2262c12e9b394146f2a550f056cef026efaa5c4f.jpg",
      "title": "全国各地的禁渔区内，都有人在公开钓鱼",
      "pubdate": 1697800720,
      "ctime": 1697800720,
      "tags": [],
      "duration": 461,
      "author": {
        "mid": 629101318,
        "name": "远方的青木",
        "face": "https://i1.hdslb.com/bfs/face/3104972aba04c34590046ecc4832fb0e2f26db4c.jpg"
      },
      "stat": {
        "aid": 234996109,
        "view": 687735,
        "danmaku": 4755,
        "reply": 2781,
        "favorite": 6374,
        "coin": 2869,
        "share": 4926,
        "now_rank": 0,
        "his_rank": 0,
        "like": 69571,
        "dislike": 0,
        "vt": 0,
        "vv": 687735
      },
      "hot_desc": "6万点赞",
      "corner_mark": 1,
      "bvid": "BV12e411R7Xb",
      "enable_vt": 0,
      "vt_display": ""
    },
    {
      "aid": 832302513,
      "type_id": 138,
      "tname": "搞笑",
      "pic": "http://i1.hdslb.com/bfs/archive/aa63bfc17726d9d897f4a81c0e2ef11079e709f0.jpg",
      "title": "一个故事",
      "pubdate": 1697604499,
      "ctime": 1697604499,
      "tags": [],
      "duration": 134,
      "author": {
        "mid": 3537113698011796,
        "name": "杨大女神呀",
        "face": "https://i1.hdslb.com/bfs/face/b23a0ca519326622d47b2de9fa57bbec10676d94.jpg"
      },
      "stat": {
        "aid": 832302513,
        "view": 1885403,
        "danmaku": 477,
        "reply": 926,
        "favorite": 9018,
        "coin": 3027,
        "share": 896,
        "now_rank": 0,
        "his_rank": 61,
        "like": 124661,
        "dislike": 0,
        "vt": 0,
        "vv": 1885403
      },
      "hot_desc": "",
      "corner_mark": 0,
      "bvid": "BV1D34y1g7Hq",
      "enable_vt": 0,
      "vt_display": ""
    },
    {
      "aid": 322178369,
      "type_id": 138,
      "tname": "搞笑",
      "pic": "http://i1.hdslb.com/bfs/archive/b40a7a375668058af9663dea41eda59bbb1bb5ac.jpg",
      "title": "余生很短，珍惜眼前人。大型纪录片《常回家看看》传奇，持续为您播出",
      "pubdate": 1697366839,
      "ctime": 1697365976,
      "tags": [],
      "duration": 136,
      "author": {
        "mid": 393469799,
        "name": "姜讲纪录片传奇",
        "face": "https://i2.hdslb.com/bfs/face/a59974a3100892ecfc7ae1b5cea19b08c9e58337.jpg"
      },
      "stat": {
        "aid": 322178369,
        "view": 1396145,
        "danmaku": 1233,
        "reply": 1949,
        "favorite": 79712,
        "coin": 54774,
        "share": 3456,
        "now_rank": 0,
        "his_rank": 31,
        "like": 125464,
        "dislike": 0,
        "vt": 0,
        "vv": 1396145
      },
      "hot_desc": "12万点赞",
      "corner_mark": 1,
      "bvid": "BV19w411z7Ns",
      "enable_vt": 0,
      "vt_display": ""
    },
    {
      "aid": 492192328,
      "type_id": 138,
      "tname": "搞笑",
      "pic": "http://i1.hdslb.com/bfs/archive/3e6d0217919e4148a7dae1d9e491b88ba0be8ef9.jpg",
      "title": "答非所问（奥义超级版）",
      "pubdate": 1697446800,
      "ctime": 1697438916,
      "tags": [],
      "duration": 722,
      "author": {
        "mid": 5970160,
        "name": "小潮院长",
        "face": "https://i1.hdslb.com/bfs/face/834eb0de8d2f470bf03e4ea92831b14f3824c863.jpg"
      },
      "stat": {
        "aid": 492192328,
        "view": 3974567,
        "danmaku": 37463,
        "reply": 5930,
        "favorite": 72320,
        "coin": 174284,
        "share": 10950,
        "now_rank": 0,
        "his_rank": 1,
        "like": 396844,
        "dislike": 0,
        "vt": 0,
        "vv": 3974567
      },
      "hot_desc": "百万播放",
      "corner_mark": 1,
      "bvid": "BV1CN41147Eo",
      "enable_vt": 0,
      "vt_display": ""
    },
    {
      "aid": 277467773,
      "type_id": 138,
      "tname": "搞笑",
      "pic": "http://i0.hdslb.com/bfs/archive/b9579456510c8468dbad5a073e383c14ee3e3c67.jpg",
      "title": "今年看过最虐的文居然是本无CP！！！",
      "pubdate": 1697792400,
      "ctime": 1697783779,
      "tags": [],
      "duration": 4471,
      "author": {
        "mid": 80991539,
        "name": "聊点什么叭",
        "face": "https://i2.hdslb.com/bfs/face/16c375fce8e259b3839a0b05285609b3aa48e8f3.jpg"
      },
      "stat": {
        "aid": 277467773,
        "view": 604809,
        "danmaku": 7235,
        "reply": 4365,
        "favorite": 19713,
        "coin": 53089,
        "share": 5772,
        "now_rank": 0,
        "his_rank": 34,
        "like": 67527,
        "dislike": 0,
        "vt": 0,
        "vv": 604809
      },
      "hot_desc": "6万点赞",
      "corner_mark": 1,
      "bvid": "BV1pw411F7mw",
      "enable_vt": 0,
      "vt_display": ""
    },
    {
      "aid": 917416687,
      "type_id": 138,
      "tname": "搞笑",
      "pic": "http://i1.hdslb.com/bfs/archive/b03aa60ca646d176814391600da1d4e21a1ba293.jpg",
      "title": "我们复刻了《闪电侠》特效【新概念慢动作挑战】",
      "pubdate": 1697859000,
      "ctime": 1697836014,
      "tags": [],
      "duration": 472,
      "author": {
        "mid": 7552204,
        "name": "啊吗粽",
        "face": "https://i1.hdslb.com/bfs/face/61fc06811d9bb41a10a932b9f95ecc3632d82799.jpg"
      },
      "stat": {
        "aid": 917416687,
        "view": 397460,
        "danmaku": 1765,
        "reply": 834,
        "favorite": 6405,
        "coin": 17723,
        "share": 766,
        "now_rank": 0,
        "his_rank": 0,
        "like": 67935,
        "dislike": 0,
        "vt": 0,
        "vv": 397460
      },
      "hot_desc": "6万点赞",
      "corner_mark": 1,
      "bvid": "BV1Mu4y1W7mY",
      "enable_vt": 0,
      "vt_display": ""
    },
    {
      "aid": 364918557,
      "type_id": 172,
      "tname": "手机游戏",
      "pic": "http://i2.hdslb.com/bfs/archive/6862142c017d50ac8dd0429049aaadc6196c8b68.jpg",
      "title": "5年前火爆全网的【旅行青蛙】为何一夜消失？如今变成什么样？",
      "pubdate": 1697803200,
      "ctime": 1697789248,
      "tags": [],
      "duration": 565,
      "author": {
        "mid": 31261235,
        "name": "L另唐",
        "face": "https://i2.hdslb.com/bfs/face/79554bb294c625c7103a219ceb84ca34ef0394e3.jpg"
      },
      "stat": {
        "aid": 364918557,
        "view": 508217,
        "danmaku": 1390,
        "reply": 1261,
        "favorite": 4344,
        "coin": 3947,
        "share": 574,
        "now_rank": 0,
        "his_rank": 0,
        "like": 21677,
        "dislike": 0,
        "vt": 0,
        "vv": 508217
      },
      "hot_desc": "",
      "corner_mark": 0,
      "bvid": "BV1L94y1L7jE",
      "enable_vt": 0,
      "vt_display": ""
    },
    {
      "aid": 234797242,
      "type_id": 250,
      "tname": "出行",
      "pic": "http://i1.hdslb.com/bfs/archive/fb4e19802ce504ad6d705cddc99ac8a67853bdfc.jpg",
      "title": "探秘全世界最离谱的球，23亿美金！ 老美到底造了个啥？",
      "pubdate": 1697706000,
      "ctime": 1697693835,
      "tags": [],
      "duration": 435,
      "author": {
        "mid": 447317111,
        "name": "Meetfood觅食",
        "face": "https://i2.hdslb.com/bfs/face/bea5c769459bddb4b955c19ce4e4dc3d8b46f8ea.jpg"
      },
      "stat": {
        "aid": 234797242,
        "view": 2657774,
        "danmaku": 6618,
        "reply": 3441,
        "favorite": 35306,
        "coin": 87096,
        "share": 7179,
        "now_rank": 0,
        "his_rank": 2,
        "like": 195893,
        "dislike": 0,
        "vt": 0,
        "vv": 2657774
      },
      "hot_desc": "百万播放",
      "corner_mark": 1,
      "bvid": "BV1p8411r7rk",
      "enable_vt": 0,
      "vt_display": ""
    },
    {
      "aid": 959892178,
      "type_id": 21,
      "tname": "日常",
      "pic": "http://i0.hdslb.com/bfs/archive/ad4ef77221d285990d1ff46317f88d51a42b7775.jpg",
      "title": "《⚡cos荧穿高跟鞋爬泰山⚡旅行者真人跑图⚡》",
      "pubdate": 1697803360,
      "ctime": 1697803360,
      "tags": [],
      "duration": 134,
      "author": {
        "mid": 179288789,
        "name": "汤面桢子",
        "face": "https://i2.hdslb.com/bfs/face/842a14133fdc86ef2161709372f95a27bccb56d5.jpg"
      },
      "stat": {
        "aid": 959892178,
        "view": 500002,
        "danmaku": 368,
        "reply": 894,
        "favorite": 8783,
        "coin": 2978,
        "share": 1221,
        "now_rank": 0,
        "his_rank": 0,
        "like": 49417,
        "dislike": 0,
        "vt": 0,
        "vv": 500002
      },
      "hot_desc": "",
      "corner_mark": 0,
      "bvid": "BV1Zp4y1T7dH",
      "enable_vt": 0,
      "vt_display": ""
    },
    {
      "aid": 449777373,
      "type_id": 138,
      "tname": "搞笑",
      "pic": "http://i1.hdslb.com/bfs/archive/2a010a18e7cf7792d3a3363e6f7d5be3915e5e7c.jpg",
      "title": "80 90后的童年回忆，小时候的迷惑行为。没有网络的时代，是怎么做到全国统一的？",
      "pubdate": 1697596200,
      "ctime": 1697558036,
      "tags": [],
      "duration": 345,
      "author": {
        "mid": 382352465,
        "name": "小胖快乐屋",
        "face": "https://i2.hdslb.com/bfs/face/aab093eedf07e061b4a32056ba32cf5498ec8678.jpg"
      },
      "stat": {
        "aid": 449777373,
        "view": 722394,
        "danmaku": 2187,
        "reply": 2216,
        "favorite": 14139,
        "coin": 16015,
        "share": 6143,
        "now_rank": 0,
        "his_rank": 0,
        "like": 34445,
        "dislike": 0,
        "vt": 0,
        "vv": 722394
      },
      "hot_desc": "",
      "corner_mark": 0,
      "bvid": "BV1Zj411x72G",
      "enable_vt": 0,
      "vt_display": ""
    },
    {
      "aid": 959841495,
      "type_id": 27,
      "tname": "综合",
      "pic": "http://i0.hdslb.com/bfs/archive/0674f4b229f572e5e43eec97bb13a2b2a2053811.jpg",
      "title": "⚡誓死保卫⚡",
      "pubdate": 1697700994,
      "ctime": 1697700995,
      "tags": [],
      "duration": 152,
      "author": {
        "mid": 412630000,
        "name": "亮_Sama",
        "face": "https://i1.hdslb.com/bfs/face/013906b5e3e932632c3bc18585b6e95417313156.jpg"
      },
      "stat": {
        "aid": 959841495,
        "view": 1328498,
        "danmaku": 464,
        "reply": 438,
        "favorite": 24628,
        "coin": 3550,
        "share": 3062,
        "now_rank": 0,
        "his_rank": 28,
        "like": 123954,
        "dislike": 0,
        "vt": 0,
        "vv": 1328498
      },
      "hot_desc": "百万播放",
      "corner_mark": 1,
      "bvid": "BV19p4y1T7G1",
      "enable_vt": 0,
      "vt_display": ""
    },
    {
      "aid": 449950517,
      "type_id": 47,
      "tname": "短片·手书",
      "pic": "http://i0.hdslb.com/bfs/archive/8f46b6b1760e86f4aa3d50b211cff4c1c7fb827d.jpg",
      "title": "【自制动画】《黄金铃》确实是帅的！！嘿嘿",
      "pubdate": 1697761835,
      "ctime": 1697761835,
      "tags": [],
      "duration": 29,
      "author": {
        "mid": 11912132,
        "name": "旋风博文",
        "face": "https://i2.hdslb.com/bfs/face/01da4060eadd3d75e3914ca6b65119d2f9da77bf.jpg"
      },
      "stat": {
        "aid": 449950517,
        "view": 1179863,
        "danmaku": 386,
        "reply": 1271,
        "favorite": 70917,
        "coin": 48170,
        "share": 4971,
        "now_rank": 0,
        "his_rank": 21,
        "like": 246865,
        "dislike": 0,
        "vt": 0,
        "vv": 1179863
      },
      "hot_desc": "百万播放",
      "corner_mark": 1,
      "bvid": "BV1oj411v7yq",
      "enable_vt": 0,
      "vt_display": ""
    },
    {
      "aid": 407359062,
      "type_id": 253,
      "tname": "动漫杂谈",
      "pic": "http://i1.hdslb.com/bfs/archive/385e7a9c4b3c7942e9335d745bc17749ba75da5d.jpg",
      "title": "《 最 喜 欢 的 一 集 》",
      "pubdate": 1697767800,
      "ctime": 1697723512,
      "tags": [],
      "duration": 363,
      "author": {
        "mid": 5870268,
        "name": "三代鹿人",
        "face": "https://i0.hdslb.com/bfs/face/a915d1a1ff921cd418e74c5711c91b23e2a18c11.jpg"
      },
      "stat": {
        "aid": 407359062,
        "view": 683506,
        "danmaku": 925,
        "reply": 871,
        "favorite": 2625,
        "coin": 2683,
        "share": 1957,
        "now_rank": 0,
        "his_rank": 0,
        "like": 46573,
        "dislike": 0,
        "vt": 0,
        "vv": 683506
      },
      "hot_desc": "",
      "corner_mark": 0,
      "bvid": "BV12G41127Ji",
      "enable_vt": 0,
      "vt_display": ""
    },
    {
      "aid": 407431032,
      "type_id": 168,
      "tname": "国产原创相关",
      "pic": "http://i0.hdslb.com/bfs/archive/1e6911162d4f32432c622982cd0a56a2080322e2.jpg",
      "title": "平A一下就加一点最大生命，这弓箭手太肉了吧",
      "pubdate": 1697791394,
      "ctime": 1697791394,
      "tags": [],
      "duration": 663,
      "author": {
        "mid": 654552,
        "name": "圆桌动漫",
        "face": "https://i0.hdslb.com/bfs/face/6c1421573d214809ca86aef25bdd23670e00128a.jpg"
      },
      "stat": {
        "aid": 407431032,
        "view": 1429587,
        "danmaku": 2134,
        "reply": 1363,
        "favorite": 32344,
        "coin": 3996,
        "share": 472,
        "now_rank": 0,
        "his_rank": 60,
        "like": 40410,
        "dislike": 0,
        "vt": 0,
        "vv": 1429587
      },
      "hot_desc": "",
      "corner_mark": 0,
      "bvid": "BV1bG411y7Nx",
      "enable_vt": 0,
      "vt_display": ""
    },
    {
      "aid": 277352521,
      "type_id": 172,
      "tname": "手机游戏",
      "pic": "http://i0.hdslb.com/bfs/archive/f5fbbbff24af2cc42e8d11d02bf4fd1527c9b800.jpg",
      "title": "魔阴身也能看懂！娱乐向解说云上五骁的扭曲身世！【泛式/星穹铁道】",
      "pubdate": 1697796000,
      "ctime": 1697714347,
      "tags": [],
      "duration": 743,
      "author": {
        "mid": 63231,
        "name": "泛式",
        "face": "https://i0.hdslb.com/bfs/face/2608aaa45309c77ac88fbfaa40e160b8c7892985.jpg"
      },
      "stat": {
        "aid": 277352521,
        "view": 673440,
        "danmaku": 4447,
        "reply": 3029,
        "favorite": 17589,
        "coin": 31097,
        "share": 13556,
        "now_rank": 0,
        "his_rank": 39,
        "like": 85345,
        "dislike": 0,
        "vt": 0,
        "vv": 673440
      },
      "hot_desc": "8万点赞",
      "corner_mark": 1,
      "bvid": "BV1Zc411f7j4",
      "enable_vt": 0,
      "vt_display": ""
    },
    {
      "aid": 534773328,
      "type_id": 126,
      "tname": "人力VOCALOID",
      "pic": "http://i2.hdslb.com/bfs/archive/48d5b1d69fb7a32633985ca625292b89e2815638.jpg",
      "title": "鬼知道我看了几遍哈哈哈",
      "pubdate": 1697603557,
      "ctime": 1697603557,
      "tags": [],
      "duration": 152,
      "author": {
        "mid": 7275647,
        "name": "碧天蓝钻",
        "face": "https://i2.hdslb.com/bfs/face/ce1595b2d2bb472bb1f5437e49cb6a2415a44147.webp"
      },
      "stat": {
        "aid": 534773328,
        "view": 1680963,
        "danmaku": 567,
        "reply": 703,
        "favorite": 9387,
        "coin": 3070,
        "share": 3918,
        "now_rank": 0,
        "his_rank": 99,
        "like": 86925,
        "dislike": 0,
        "vt": 0,
        "vv": 1680963
      },
      "hot_desc": "百万播放",
      "corner_mark": 1,
      "bvid": "BV1Yu411T7Bc",
      "enable_vt": 0,
      "vt_display": ""
    },
    {
      "aid": 364911487,
      "type_id": 218,
      "tname": "喵星人",
      "pic": "http://i2.hdslb.com/bfs/archive/37f86cfa14861d33bef9b8696360957f6350529d.jpg",
      "title": "我在猫房子里给老鼠建了个家",
      "pubdate": 1697796000,
      "ctime": 1697792066,
      "tags": [],
      "duration": 112,
      "author": {
        "mid": 295993972,
        "name": "爱鼓捣的邢志磊",
        "face": "https://i1.hdslb.com/bfs/face/089170383115daac0772509a45c0dd2564426354.jpg"
      },
      "stat": {
        "aid": 364911487,
        "view": 862620,
        "danmaku": 467,
        "reply": 683,
        "favorite": 9405,
        "coin": 10243,
        "share": 6094,
        "now_rank": 0,
        "his_rank": 0,
        "like": 69719,
        "dislike": 0,
        "vt": 0,
        "vv": 862620
      },
      "hot_desc": "6万点赞",
      "corner_mark": 1,
      "bvid": "BV1G94y1L7hS",
      "enable_vt": 0,
      "vt_display": ""
    },
    {
      "aid": 492443712,
      "type_id": 28,
      "tname": "原创音乐",
      "pic": "http://i0.hdslb.com/bfs/archive/9556337ffa30f43368bd7c384a39df5b4c0b75bb.jpg",
      "title": "“是家具，不是刑具”",
      "pubdate": 1697803537,
      "ctime": 1697803155,
      "tags": [],
      "duration": 140,
      "author": {
        "mid": 17134369,
        "name": "司墨尧smile",
        "face": "https://i1.hdslb.com/bfs/face/c0633737a7d7d7a2b53cd682eda4dc7c5b509247.jpg"
      },
      "stat": {
        "aid": 492443712,
        "view": 313963,
        "danmaku": 64,
        "reply": 208,
        "favorite": 2135,
        "coin": 743,
        "share": 317,
        "now_rank": 0,
        "his_rank": 0,
        "like": 19016,
        "dislike": 0,
        "vt": 0,
        "vv": 313963
      },
      "hot_desc": "",
      "corner_mark": 0,
      "bvid": "BV1tN411x7CJ",
      "enable_vt": 0,
      "vt_display": ""
    },
    {
      "aid": 364898947,
      "type_id": 216,
      "tname": "鬼畜剧场",
      "pic": "http://i0.hdslb.com/bfs/archive/33f7fb8d7a25bfdd9ee4344d1e9c919073dd1c3f.jpg",
      "title": "“Cheems，要去码头整点和平吗？”",
      "pubdate": 1697773500,
      "ctime": 1697767371,
      "tags": [],
      "duration": 205,
      "author": {
        "mid": 1123353719,
        "name": "万灵缝合厂",
        "face": "https://i2.hdslb.com/bfs/face/5b83b14a9ba161c9166523a68628cd854cbeb832.jpg"
      },
      "stat": {
        "aid": 364898947,
        "view": 899744,
        "danmaku": 1812,
        "reply": 844,
        "favorite": 18686,
        "coin": 17551,
        "share": 2580,
        "now_rank": 0,
        "his_rank": 31,
        "like": 101923,
        "dislike": 0,
        "vt": 0,
        "vv": 899744
      },
      "hot_desc": "10万点赞",
      "corner_mark": 1,
      "bvid": "BV1s94y1b77h",
      "enable_vt": 0,
      "vt_display": ""
    },
    {
      "aid": 322350136,
      "type_id": 21,
      "tname": "日常",
      "pic": "http://i2.hdslb.com/bfs/archive/fe44fc6a75166f7dfa0e280c329109b85fb5e348.jpg",
      "title": "不愧是曾经亚洲第一的大学，氛围太好了！",
      "pubdate": 1697646737,
      "ctime": 1697646738,
      "tags": [],
      "duration": 98,
      "author": {
        "mid": 501493255,
        "name": "余帅的名校行",
        "face": "https://i1.hdslb.com/bfs/face/bb587a0065f2e74ba0015f74eb7883172b28fc3b.jpg"
      },
      "stat": {
        "aid": 322350136,
        "view": 1547880,
        "danmaku": 0,
        "reply": 33,
        "favorite": 12862,
        "coin": 2210,
        "share": 3976,
        "now_rank": 0,
        "his_rank": 0,
        "like": 80319,
        "dislike": 0,
        "vt": 0,
        "vv": 1547880
      },
      "hot_desc": "百万播放",
      "corner_mark": 1,
      "bvid": "BV12w41167gJ",
      "enable_vt": 0,
      "vt_display": ""
    },
    {
      "aid": 789960532,
      "type_id": 138,
      "tname": "搞笑",
      "pic": "http://i0.hdslb.com/bfs/archive/2b0586bb9874906090fc4a90452ddd3af92b1864.jpg",
      "title": "趁兄弟宿醉连人带床给他搬到大街上！再把他衣服换成蜜蜂装！！",
      "pubdate": 1697795100,
      "ctime": 1697788699,
      "tags": [],
      "duration": 516,
      "author": {
        "mid": 10272440,
        "name": "骚拳超人",
        "face": "https://i2.hdslb.com/bfs/face/4d3db1c6e0ada8478c190c8ef217a6d013b34809.jpg"
      },
      "stat": {
        "aid": 789960532,
        "view": 719783,
        "danmaku": 4838,
        "reply": 1169,
        "favorite": 4473,
        "coin": 16490,
        "share": 8762,
        "now_rank": 0,
        "his_rank": 0,
        "like": 47237,
        "dislike": 0,
        "vt": 0,
        "vv": 719783
      },
      "hot_desc": "",
      "corner_mark": 0,
      "bvid": "BV15y4y1P74A",
      "enable_vt": 0,
      "vt_display": ""
    },
    {
      "aid": 277374581,
      "type_id": 182,
      "tname": "影视杂谈",
      "pic": "http://i1.hdslb.com/bfs/archive/fbd81962a0dfcac046513526ffc2254e3ddd5d8a.jpg",
      "title": "胡宗宪的权术有多高？如何看懂人精的潜台词？国产第一神剧深度拆解！第五回",
      "pubdate": 1697857500,
      "ctime": 1697734863,
      "tags": [],
      "duration": 2527,
      "author": {
        "mid": 2083634390,
        "name": "一条闲木鱼",
        "face": "https://i2.hdslb.com/bfs/face/1b0e9d05e20c6fc08df34a98f24260e94167aaf2.jpg"
      },
      "stat": {
        "aid": 277374581,
        "view": 199448,
        "danmaku": 1319,
        "reply": 405,
        "favorite": 4861,
        "coin": 18081,
        "share": 318,
        "now_rank": 0,
        "his_rank": 0,
        "like": 20209,
        "dislike": 0,
        "vt": 0,
        "vv": 199448
      },
      "hot_desc": "",
      "corner_mark": 0,
      "bvid": "BV19c411f7b5",
      "enable_vt": 0,
      "vt_display": ""
    },
    {
      "aid": 874831883,
      "type_id": 212,
      "tname": "美食侦探",
      "pic": "http://i2.hdslb.com/bfs/archive/da1a56668d9da78acd9656c47c5c4c6c94208de7.jpg",
      "title": "串串香自助自助挑战1200串记录，七分饱刚好！",
      "pubdate": 1697685991,
      "ctime": 1697685991,
      "tags": [],
      "duration": 311,
      "author": {
        "mid": 3493285251254309,
        "name": "-牛哥不牛-",
        "face": "https://i2.hdslb.com/bfs/face/fc5b159f7829afb9f91223ff7bdbde7e9a6d08cc.jpg"
      },
      "stat": {
        "aid": 874831883,
        "view": 808132,
        "danmaku": 342,
        "reply": 285,
        "favorite": 6770,
        "coin": 607,
        "share": 281,
        "now_rank": 0,
        "his_rank": 0,
        "like": 35422,
        "dislike": 0,
        "vt": 0,
        "vv": 808132
      },
      "hot_desc": "",
      "corner_mark": 0,
      "bvid": "BV1TN4y1C7KZ",
      "enable_vt": 0,
      "vt_display": ""
    },
    {
      "aid": 234965821,
      "type_id": 171,
      "tname": "电子竞技",
      "pic": "http://i2.hdslb.com/bfs/archive/bb2abe85c912c39f4583847aa944c09a407e5012.jpg",
      "title": "公益纪录片《江河的微笑》｜江河的孩子，我们共生共悦",
      "pubdate": 1697857200,
      "ctime": 1697802126,
      "tags": [],
      "duration": 790,
      "author": {
        "mid": 57863910,
        "name": "王者荣耀",
        "face": "https://i0.hdslb.com/bfs/face/b98606398da2891c4089cf630c28a365e062fee8.jpg"
      },
      "stat": {
        "aid": 234965821,
        "view": 193387,
        "danmaku": 96,
        "reply": 492,
        "favorite": 780,
        "coin": 1382,
        "share": 202,
        "now_rank": 0,
        "his_rank": 0,
        "like": 13061,
        "dislike": 0,
        "vt": 0,
        "vv": 193387
      },
      "hot_desc": "",
      "corner_mark": 0,
      "bvid": "BV1ie411R7Ch",
      "enable_vt": 0,
      "vt_display": ""
    },
    {
      "aid": 874988939,
      "type_id": 201,
      "tname": "科学科普",
      "pic": "http://i0.hdslb.com/bfs/archive/dfa6d331fee660415b1cb65fcfa80fa7140ca0e5.jpg",
      "title": "盲人看到的世界，是什么样的？",
      "pubdate": 1697857200,
      "ctime": 1697816066,
      "tags": [],
      "duration": 347,
      "author": {
        "mid": 1195284234,
        "name": "李白尼的猜想",
        "face": "https://i0.hdslb.com/bfs/face/a1faae3e1943c67e0a88ad1af7329aeed7d4616b.jpg"
      },
      "stat": {
        "aid": 874988939,
        "view": 269635,
        "danmaku": 780,
        "reply": 568,
        "favorite": 4280,
        "coin": 7684,
        "share": 354,
        "now_rank": 0,
        "his_rank": 0,
        "like": 27366,
        "dislike": 0,
        "vt": 0,
        "vv": 269635
      },
      "hot_desc": "很多人点赞",
      "corner_mark": 1,
      "bvid": "BV1RN4y1C7TK",
      "enable_vt": 0,
      "vt_display": ""
    },
    {
      "aid": 704809931,
      "type_id": 216,
      "tname": "鬼畜剧场",
      "pic": "http://i0.hdslb.com/bfs/archive/44f00a1a1e58dd6b4aab2f59868135d343d01566.jpg",
      "title": "霸道军阀爱上平民教师",
      "pubdate": 1697732547,
      "ctime": 1697732547,
      "tags": [],
      "duration": 119,
      "author": {
        "mid": 387086717,
        "name": "Van-奇",
        "face": "https://i2.hdslb.com/bfs/face/e4556baf79231372bb188806c6096a95c02c5041.jpg"
      },
      "stat": {
        "aid": 704809931,
        "view": 904514,
        "danmaku": 949,
        "reply": 1201,
        "favorite": 10254,
        "coin": 5540,
        "share": 5107,
        "now_rank": 0,
        "his_rank": 0,
        "like": 68470,
        "dislike": 0,
        "vt": 0,
        "vv": 904514
      },
      "hot_desc": "6万点赞",
      "corner_mark": 1,
      "bvid": "BV1aQ4y1s7QY",
      "enable_vt": 0,
      "vt_display": ""
    },
    {
      "aid": 234788580,
      "type_id": 182,
      "tname": "影视杂谈",
      "pic": "http://i1.hdslb.com/bfs/archive/9aee69ca28d7ddb4e6914a266d2f558f9fcc18a4.jpg",
      "title": "158万人打出9.0的逆天高分，阿米尔汗的又一封神之作",
      "pubdate": 1697727665,
      "ctime": 1697727665,
      "tags": [],
      "duration": 968,
      "author": {
        "mid": 430082207,
        "name": "云晨电影",
        "face": "https://i2.hdslb.com/bfs/face/95b7820a64e35d6f504399bd41540a48590366c0.jpg"
      },
      "stat": {
        "aid": 234788580,
        "view": 689814,
        "danmaku": 1195,
        "reply": 608,
        "favorite": 8170,
        "coin": 8422,
        "share": 414,
        "now_rank": 0,
        "his_rank": 0,
        "like": 54370,
        "dislike": 0,
        "vt": 0,
        "vv": 689814
      },
      "hot_desc": "5万点赞",
      "corner_mark": 1,
      "bvid": "BV1n8411r7kH",
      "enable_vt": 0,
      "vt_display": ""
    },
    {
      "aid": 747261820,
      "type_id": 138,
      "tname": "搞笑",
      "pic": "http://i1.hdslb.com/bfs/archive/0766766addfb2f917b7f86995b4ae037969d5988.jpg",
      "title": "【误 入 大 电 音 寺】",
      "pubdate": 1697533325,
      "ctime": 1697532043,
      "tags": [],
      "duration": 237,
      "author": {
        "mid": 3380239,
        "name": "神奇的老皮",
        "face": "https://i1.hdslb.com/bfs/face/e7c191e9be6764107415069b36f7d9564f149c86.gif"
      },
      "stat": {
        "aid": 747261820,
        "view": 3527603,
        "danmaku": 5890,
        "reply": 3322,
        "favorite": 54086,
        "coin": 79586,
        "share": 30103,
        "now_rank": 0,
        "his_rank": 1,
        "like": 291687,
        "dislike": 0,
        "vt": 0,
        "vv": 3527603
      },
      "hot_desc": "百万播放",
      "corner_mark": 1,
      "bvid": "BV16C4y1G7Nk",
      "enable_vt": 0,
      "vt_display": ""
    },
    {
      "aid": 959660475,
      "type_id": 250,
      "tname": "出行",
      "pic": "http://i1.hdslb.com/bfs/archive/83d962103e3ae76a44d962b038931a62e9c11723.jpg",
      "title": "偶遇河南老乡给我了100块钱，推了20公里坡天黑在海拔4800米垭口露营雪花纷飞寒风凛冽冻成狗了！",
      "pubdate": 1697461525,
      "ctime": 1697461525,
      "tags": [],
      "duration": 1070,
      "author": {
        "mid": 1727750599,
        "name": "小辉漂流记",
        "face": "https://i1.hdslb.com/bfs/face/a27581acf7e3892926e23f49ec449a3447246e7a.jpg"
      },
      "stat": {
        "aid": 959660475,
        "view": 3846334,
        "danmaku": 9730,
        "reply": 6158,
        "favorite": 20970,
        "coin": 103738,
        "share": 9936,
        "now_rank": 0,
        "his_rank": 4,
        "like": 246133,
        "dislike": 0,
        "vt": 0,
        "vv": 3846334
      },
      "hot_desc": "百万播放",
      "corner_mark": 1,
      "bvid": "BV18p4y1u7u4",
      "enable_vt": 0,
      "vt_display": ""
    },
    {
      "aid": 874985813,
      "type_id": 21,
      "tname": "日常",
      "pic": "http://i2.hdslb.com/bfs/archive/2e9fc773479fff793d7b928070f419048a15f187.png",
      "title": "【全新监管者——“愚人金”】将于10月23日上线共研服，技能展示视频如下#第五人格记忆余烬##第五人格愚人金##第五人格#",
      "pubdate": 1697868128,
      "ctime": 1697868128,
      "tags": [],
      "duration": 140,
      "author": {
        "mid": 211005705,
        "name": "网易第五人格手游",
        "face": "https://i0.hdslb.com/bfs/face/c862c0216a236d0c1f3a8b578fc047bb4b66ba95.jpg"
      },
      "stat": {
        "aid": 874985813,
        "view": 342642,
        "danmaku": 1372,
        "reply": 3044,
        "favorite": 3079,
        "coin": 2195,
        "share": 15499,
        "now_rank": 0,
        "his_rank": 0,
        "like": 28488,
        "dislike": 0,
        "vt": 0,
        "vv": 342642
      },
      "hot_desc": "1万分享",
      "corner_mark": 1,
      "bvid": "BV1AN4y1y7nQ",
      "enable_vt": 0,
      "vt_display": ""
    },
    {
      "aid": 492435973,
      "type_id": 171,
      "tname": "电子竞技",
      "pic": "http://i1.hdslb.com/bfs/archive/edab7f8426f38ae2d129ed06dc79be009183a9cf.jpg",
      "title": "【S13全球总决赛】10月20日 瑞士轮第二轮 G2 vs WBG",
      "pubdate": 1697800211,
      "ctime": 1697800211,
      "tags": [],
      "duration": 4159,
      "author": {
        "mid": 50329118,
        "name": "哔哩哔哩英雄联盟赛事",
        "face": "https://i2.hdslb.com/bfs/face/544c89e68f2b1f12ffcbb8b3c062a3328e8692d9.jpg"
      },
      "stat": {
        "aid": 492435973,
        "view": 1662638,
        "danmaku": 14493,
        "reply": 7580,
        "favorite": 1606,
        "coin": 1895,
        "share": 1351,
        "now_rank": 0,
        "his_rank": 0,
        "like": 16603,
        "dislike": 0,
        "vt": 0,
        "vv": 1662638
      },
      "hot_desc": "",
      "corner_mark": 0,
      "bvid": "BV1LN411x7CK",
      "enable_vt": 0,
      "vt_display": ""
    },
    {
      "aid": 619911744,
      "type_id": 17,
      "tname": "单机游戏",
      "pic": "http://i2.hdslb.com/bfs/archive/81dd08424a29534b8a7f2a7545c6eca1e68a5cfd.jpg",
      "title": "漫威蜘蛛侠 2 #1，城市里出现了沙子巨人！",
      "pubdate": 1697882702,
      "ctime": 1697882703,
      "tags": [],
      "duration": 3340,
      "author": {
        "mid": 15634833,
        "name": "鲤鱼Ace",
        "face": "http://i0.hdslb.com/bfs/face/556617d09ef2b968f4bd2d7a0f5d08a206352ec1.jpg"
      },
      "stat": {
        "aid": 619911744,
        "view": 93557,
        "danmaku": 3138,
        "reply": 864,
        "favorite": 2378,
        "coin": 3437,
        "share": 172,
        "now_rank": 0,
        "his_rank": 0,
        "like": 11466,
        "dislike": 0,
        "vt": 0,
        "vv": 93557
      },
      "hot_desc": "",
      "corner_mark": 0,
      "bvid": "BV1c84y1o7of",
      "enable_vt": 0,
      "vt_display": ""
    },
    {
      "aid": 407457927,
      "type_id": 201,
      "tname": "科学科普",
      "pic": "http://i1.hdslb.com/bfs/archive/c1d11eb8208b136fee47f1b3fd4d4623ce884bc5.jpg",
      "title": "不可思议的“干水”，摸起来和面粉一样，为什么会是液体？",
      "pubdate": 1697794741,
      "ctime": 1697787766,
      "tags": [],
      "duration": 213,
      "author": {
        "mid": 630874464,
        "name": "冷科普",
        "face": "https://i0.hdslb.com/bfs/face/58f9464e3a375648066f6a6f0cf57e6edd7ebf44.jpg"
      },
      "stat": {
        "aid": 407457927,
        "view": 1386029,
        "danmaku": 987,
        "reply": 862,
        "favorite": 6246,
        "coin": 702,
        "share": 719,
        "now_rank": 0,
        "his_rank": 0,
        "like": 39082,
        "dislike": 0,
        "vt": 0,
        "vv": 1386029
      },
      "hot_desc": "",
      "corner_mark": 0,
      "bvid": "BV1qG411y7zZ",
      "enable_vt": 0,
      "vt_display": ""
    },
    {
      "aid": 747428546,
      "type_id": 27,
      "tname": "综合",
      "pic": "http://i0.hdslb.com/bfs/archive/5951bc0122212acfe84179534c42d5ca43e02c27.jpg",
      "title": "⚡ 道 长 啊 ？！ ⚡",
      "pubdate": 1697860800,
      "ctime": 1697846606,
      "tags": [],
      "duration": 152,
      "author": {
        "mid": 1486340861,
        "name": "夏露露Ruru",
        "face": "https://i2.hdslb.com/bfs/face/40851c0e2493ac3bafb747423ec204d670c84b33.jpg"
      },
      "stat": {
        "aid": 747428546,
        "view": 309255,
        "danmaku": 414,
        "reply": 309,
        "favorite": 1673,
        "coin": 1522,
        "share": 389,
        "now_rank": 0,
        "his_rank": 0,
        "like": 28523,
        "dislike": 0,
        "vt": 0,
        "vv": 309255
      },
      "hot_desc": "动画综合·人气飙升",
      "corner_mark": 1,
      "bvid": "BV1DC4y1g7n8",
      "enable_vt": 0,
      "vt_display": ""
    },
    {
      "aid": 619887128,
      "type_id": 86,
      "tname": "特摄",
      "pic": "http://i0.hdslb.com/bfs/archive/b1f831cc42081dc4480b1201d0c7ea9ddae13ff2.jpg",
      "title": "【布莱泽奥特曼吐槽】呀咩那塞！我们这是空想特摄，不是人民的名义",
      "pubdate": 1697842563,
      "ctime": 1697842563,
      "tags": [],
      "duration": 781,
      "author": {
        "mid": 33729931,
        "name": "九冢嵬",
        "face": "https://i1.hdslb.com/bfs/face/c4118df024482084f5c477be3207beffaf487a0c.jpg"
      },
      "stat": {
        "aid": 619887128,
        "view": 426848,
        "danmaku": 2158,
        "reply": 1391,
        "favorite": 8806,
        "coin": 21330,
        "share": 1731,
        "now_rank": 0,
        "his_rank": 0,
        "like": 50863,
        "dislike": 0,
        "vt": 0,
        "vv": 426848
      },
      "hot_desc": "5万点赞",
      "corner_mark": 1,
      "bvid": "BV1984y1d7zo",
      "enable_vt": 0,
      "vt_display": ""
    },
    {
      "aid": 364936781,
      "type_id": 171,
      "tname": "电子竞技",
      "pic": "http://i0.hdslb.com/bfs/archive/feeb261ec6e05745ee2a62213046671eeb8bf4ba.jpg",
      "title": "【解读S13】中路有罪，但不全是小虎的问题！复盘WBG领先一万经济惨遭G2翻盘！",
      "pubdate": 1697844138,
      "ctime": 1697844138,
      "tags": [],
      "duration": 968,
      "author": {
        "mid": 6731340,
        "name": "分析师蓝宝石",
        "face": "https://i0.hdslb.com/bfs/baselabs/187ab068372228cb3b9cc2e83df6c02499df697b.jpg"
      },
      "stat": {
        "aid": 364936781,
        "view": 493234,
        "danmaku": 2213,
        "reply": 2853,
        "favorite": 2077,
        "coin": 13722,
        "share": 950,
        "now_rank": 0,
        "his_rank": 0,
        "like": 25674,
        "dislike": 0,
        "vt": 0,
        "vv": 493234
      },
      "hot_desc": "",
      "corner_mark": 0,
      "bvid": "BV1u94y1L7kj",
      "enable_vt": 0,
      "vt_display": ""
    },
    {
      "aid": 874986212,
      "type_id": 182,
      "tname": "影视杂谈",
      "pic": "http://i1.hdslb.com/bfs/archive/850d19f4fe564876b6279ec4489216e1949662f7.jpg",
      "title": "《田耕纪》：穿到种田系统，搞钱种地斗亲戚！",
      "pubdate": 1697854800,
      "ctime": 1697811241,
      "tags": [],
      "duration": 876,
      "author": {
        "mid": 34189415,
        "name": "low君热剧",
        "face": "https://i2.hdslb.com/bfs/face/fabe17ef4b344336b872e3ded46a4a4b11140e7f.jpg"
      },
      "stat": {
        "aid": 874986212,
        "view": 320992,
        "danmaku": 2495,
        "reply": 1380,
        "favorite": 2358,
        "coin": 3756,
        "share": 1081,
        "now_rank": 0,
        "his_rank": 0,
        "like": 17631,
        "dislike": 0,
        "vt": 0,
        "vv": 320992
      },
      "hot_desc": "",
      "corner_mark": 0,
      "bvid": "BV1AN4y1y7WR",
      "enable_vt": 0,
      "vt_display": ""
    },
    {
      "aid": 449650746,
      "type_id": 130,
      "tname": "音乐综合",
      "pic": "http://i1.hdslb.com/bfs/archive/6936658adffe40b1c90b7df3cebd887d2f2fcff8.jpg",
      "title": "那些只打高端局的BGM",
      "pubdate": 1697291844,
      "ctime": 1697291844,
      "tags": [],
      "duration": 216,
      "author": {
        "mid": 524902490,
        "name": "想喝香芋奶",
        "face": "https://i2.hdslb.com/bfs/face/63a047a385f4afbc29de833a3b2475eca61a340c.jpg"
      },
      "stat": {
        "aid": 449650746,
        "view": 1183192,
        "danmaku": 419,
        "reply": 310,
        "favorite": 176609,
        "coin": 12554,
        "share": 229,
        "now_rank": 0,
        "his_rank": 0,
        "like": 43799,
        "dislike": 0,
        "vt": 0,
        "vv": 1183192
      },
      "hot_desc": "",
      "corner_mark": 0,
      "bvid": "BV1Hj411x7P8",
      "enable_vt": 0,
      "vt_display": ""
    },
    {
      "aid": 492448381,
      "type_id": 95,
      "tname": "数码",
      "pic": "http://i2.hdslb.com/bfs/archive/0be56ee8232b11211a902934612da27663b7c512.jpg",
      "title": "怨种还是大捡漏？一万块买100张纸？【怪东西分享3.0】",
      "pubdate": 1697792400,
      "ctime": 1697791436,
      "tags": [],
      "duration": 880,
      "author": {
        "mid": 946974,
        "name": "影视飓风",
        "face": "https://i0.hdslb.com/bfs/face/c1733474892caa45952b2c09a89323157df7129a.jpg"
      },
      "stat": {
        "aid": 492448381,
        "view": 651804,
        "danmaku": 3903,
        "reply": 933,
        "favorite": 7967,
        "coin": 24810,
        "share": 1238,
        "now_rank": 0,
        "his_rank": 94,
        "like": 70587,
        "dislike": 0,
        "vt": 0,
        "vv": 651804
      },
      "hot_desc": "7万点赞",
      "corner_mark": 1,
      "bvid": "BV18N411x7NZ",
      "enable_vt": 0,
      "vt_display": ""
    },
    {
      "aid": 577343993,
      "type_id": 21,
      "tname": "日常",
      "pic": "http://i0.hdslb.com/bfs/archive/7065e49cc7474f188a14327e0c5ed21e0599858e.jpg",
      "title": "人生建议：不要轻易买别墅！尤其是在芬兰",
      "pubdate": 1697713170,
      "ctime": 1697713171,
      "tags": [],
      "duration": 218,
      "author": {
        "mid": 48040948,
        "name": "北极圈芬兰大鱼real",
        "face": "https://i1.hdslb.com/bfs/face/5a24ce0832ea0f0ec4d2ee768a1aa4dd9c138658.jpg"
      },
      "stat": {
        "aid": 577343993,
        "view": 1262762,
        "danmaku": 1747,
        "reply": 2682,
        "favorite": 9071,
        "coin": 4631,
        "share": 11563,
        "now_rank": 0,
        "his_rank": 50,
        "like": 106821,
        "dislike": 0,
        "vt": 0,
        "vv": 1262762
      },
      "hot_desc": "百万播放",
      "corner_mark": 1,
      "bvid": "BV1WB4y1o7C4",
      "enable_vt": 0,
      "vt_display": ""
    },
    {
      "aid": 704893568,
      "type_id": 228,
      "tname": "人文历史",
      "pic": "http://i1.hdslb.com/bfs/archive/b70eb77fd796bb1d23643aab87c6d726fd2be282.jpg",
      "title": "我不吃牛肉！真实历史上的“狗军阀”曹锳【民国小史38】",
      "pubdate": 1697797200,
      "ctime": 1697782756,
      "tags": [],
      "duration": 508,
      "author": {
        "mid": 396071811,
        "name": "苏维埃班长",
        "face": "https://i0.hdslb.com/bfs/face/ee000a7c81838d1826fac8b4b2ef91841b714af8.jpg"
      },
      "stat": {
        "aid": 704893568,
        "view": 744947,
        "danmaku": 758,
        "reply": 928,
        "favorite": 3158,
        "coin": 551,
        "share": 260,
        "now_rank": 0,
        "his_rank": 0,
        "like": 20153,
        "dislike": 0,
        "vt": 0,
        "vv": 744947
      },
      "hot_desc": "",
      "corner_mark": 0,
      "bvid": "BV1SQ4y1s75U",
      "enable_vt": 0,
      "vt_display": ""
    },
    {
      "aid": 319878652,
      "type_id": 17,
      "tname": "单机游戏",
      "pic": "http://i0.hdslb.com/bfs/archive/8ed832c53bcf6ad7939d2d995bbb6b87e29d1369.jpg",
      "title": "当你受到攻击就会「直接变小」？！",
      "pubdate": 1697846400,
      "ctime": 1697805252,
      "tags": [],
      "duration": 878,
      "author": {
        "mid": 14890801,
        "name": "大炒面制造者Cen",
        "face": "https://i1.hdslb.com/bfs/face/ddbd161cff620238122005fdbe232668c4e964ab.jpg"
      },
      "stat": {
        "aid": 319878652,
        "view": 423977,
        "danmaku": 1900,
        "reply": 384,
        "favorite": 4855,
        "coin": 7556,
        "share": 248,
        "now_rank": 0,
        "his_rank": 0,
        "like": 48951,
        "dislike": 0,
        "vt": 0,
        "vv": 423977
      },
      "hot_desc": "单机游戏·人气飙升",
      "corner_mark": 1,
      "bvid": "BV1Mw411X7hi",
      "enable_vt": 0,
      "vt_display": ""
    },
    {
      "aid": 747328114,
      "type_id": 22,
      "tname": "鬼畜调教",
      "pic": "http://i0.hdslb.com/bfs/archive/85fdeccb606d7c3a57cc81b6968214c6d30b773a.jpg",
      "title": "“谁教你这么剪的，你把人笑拥了！”",
      "pubdate": 1697706000,
      "ctime": 1697696498,
      "tags": [],
      "duration": 101,
      "author": {
        "mid": 250648682,
        "name": "红豆稀饭中",
        "face": "https://i2.hdslb.com/bfs/face/3dc6737d4ab6e8d0390409af88e9d24c3056a53b.jpg"
      },
      "stat": {
        "aid": 747328114,
        "view": 1130135,
        "danmaku": 1010,
        "reply": 1228,
        "favorite": 20843,
        "coin": 34239,
        "share": 7257,
        "now_rank": 0,
        "his_rank": 45,
        "like": 124155,
        "dislike": 0,
        "vt": 0,
        "vv": 1130135
      },
      "hot_desc": "百万播放",
      "corner_mark": 1,
      "bvid": "BV1wC4y1V7qD",
      "enable_vt": 0,
      "vt_display": ""
    },
    {
      "aid": 322169524,
      "type_id": 122,
      "tname": "野生技能协会",
      "pic": "http://i1.hdslb.com/bfs/archive/16de091337588f33eac138b777306207797b3d57.jpg",
      "title": "教你学会林尼空手出牌",
      "pubdate": 1697371200,
      "ctime": 1697364185,
      "tags": [],
      "duration": 203,
      "author": {
        "mid": 1373108335,
        "name": "玩魔术的苟初一",
        "face": "https://i1.hdslb.com/bfs/face/1d1d36b435a19337e61e0a18e98ffc3649274898.jpg"
      },
      "stat": {
        "aid": 322169524,
        "view": 1696768,
        "danmaku": 440,
        "reply": 406,
        "favorite": 156674,
        "coin": 16412,
        "share": 2771,
        "now_rank": 0,
        "his_rank": 11,
        "like": 175866,
        "dislike": 0,
        "vt": 0,
        "vv": 1696768
      },
      "hot_desc": "百万播放",
      "corner_mark": 1,
      "bvid": "BV1pw411k7Tf",
      "enable_vt": 0,
      "vt_display": ""
    }
  ],
  "message": "0",
  "page": {
    "count": 500,
    "pn": 1,
    "ps": 100
  }
}
```

### 返回结果

|状态码|状态码含义|说明|数据模型|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|成功|Inline|

### 返回数据结构

状态码 **200**

|名称|类型|必选|约束|中文名|说明|
|---|---|---|---|---|---|
|» code|integer|true|none||none|
|» data|[object]|true|none||none|
|»» aid|integer|true|none||none|
|»» type_id|integer|true|none||none|
|»» tname|string|true|none||none|
|»» pic|string|true|none||none|
|»» title|string|true|none||none|
|»» pubdate|integer|true|none||none|
|»» ctime|integer|true|none||none|
|»» tags|[string]|true|none||none|
|»» duration|integer|true|none||none|
|»» author|object|true|none||none|
|»»» mid|integer|true|none||none|
|»»» name|string|true|none||none|
|»»» face|string|true|none||none|
|»» stat|object|true|none||none|
|»»» aid|integer|true|none||none|
|»»» view|integer|true|none||none|
|»»» danmaku|integer|true|none||none|
|»»» reply|integer|true|none||none|
|»»» favorite|integer|true|none||none|
|»»» coin|integer|true|none||none|
|»»» share|integer|true|none||none|
|»»» now_rank|integer|true|none||none|
|»»» his_rank|integer|true|none||none|
|»»» like|integer|true|none||none|
|»»» dislike|integer|true|none||none|
|»»» vt|integer|true|none||none|
|»»» vv|integer|true|none||none|
|»» hot_desc|string|true|none||none|
|»» corner_mark|integer|true|none||none|
|»» bvid|string|true|none||none|
|»» enable_vt|integer|true|none||none|
|»» vt_display|string|true|none||none|
|» message|string|true|none||none|
|» page|object|true|none||none|
|»» count|integer|true|none||none|
|»» pn|integer|true|none||none|
|»» ps|integer|true|none||none|

## GET 热门推荐 (PC)

GET /x/web-interface/wbi/index/top/feed/rcmd

### 请求参数

|名称|位置|类型|必选|说明|
|---|---|---|---|---|
|web_location|query|string| 否 |none|
|y_num|query|string| 否 |none|
|fresh_type|query|string| 否 |none|
|feed_version|query|string| 否 |none|
|fresh_idx_1h|query|string| 否 |none|
|fetch_row|query|string| 否 |none|
|fresh_idx|query|string| 否 |none|
|brush|query|string| 否 |none|
|homepage_ver|query|string| 否 |none|
|ps|query|string| 否 |none|
|last_y_num|query|string| 否 |none|
|screen|query|string| 否 |none|
|seo_info|query|string| 否 |none|
|last_showlist|query|string| 否 |none|
|uniq_id|query|string| 否 |none|
|User-Agent|header|string| 否 |none|

> 返回示例

> 200 Response

```json
{
  "code": 0,
  "message": "string",
  "ttl": 0,
  "data": {
    "item": [
      {
        "id": 0,
        "bvid": "string",
        "cid": 0,
        "goto": "string",
        "uri": "string",
        "pic": "string",
        "pic_4_3": "string",
        "title": "string",
        "duration": 0,
        "pubdate": 0,
        "owner": {
          "mid": 0,
          "name": "string",
          "face": "string"
        },
        "stat": {
          "view": 0,
          "like": 0,
          "danmaku": 0,
          "vt": 0
        },
        "av_feature": null,
        "is_followed": 0,
        "rcmd_reason": null,
        "show_info": 0,
        "track_id": "string",
        "pos": 0,
        "room_info": null,
        "ogv_info": null,
        "business_info": null,
        "is_stock": 0,
        "enable_vt": 0,
        "vt_display": "string"
      }
    ],
    "side_bar_column": null,
    "business_card": null,
    "floor_info": null,
    "user_feature": null,
    "preload_expose_pct": 0,
    "preload_floor_expose_pct": 0,
    "mid": 0
  }
}
```

### 返回结果

|状态码|状态码含义|说明|数据模型|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|成功|Inline|

### 返回数据结构

状态码 **200**

|名称|类型|必选|约束|中文名|说明|
|---|---|---|---|---|---|
|» code|integer|true|none||none|
|» message|string|true|none||none|
|» ttl|integer|true|none||none|
|» data|object|true|none||none|
|»» item|[object]|true|none||none|
|»»» id|integer|true|none||none|
|»»» bvid|string|true|none||none|
|»»» cid|integer|true|none||none|
|»»» goto|string|true|none||none|
|»»» uri|string|true|none||none|
|»»» pic|string|true|none||none|
|»»» pic_4_3|string|true|none||none|
|»»» title|string|true|none||none|
|»»» duration|integer|true|none||none|
|»»» pubdate|integer|true|none||none|
|»»» owner|object|true|none||none|
|»»»» mid|integer|true|none||none|
|»»»» name|string|true|none||none|
|»»»» face|string|true|none||none|
|»»» stat|object|true|none||none|
|»»»» view|integer|true|none||none|
|»»»» like|integer|true|none||none|
|»»»» danmaku|integer|true|none||none|
|»»»» vt|integer|true|none||none|
|»»» av_feature|null|true|none||none|
|»»» is_followed|integer|true|none||none|
|»»» rcmd_reason|null|true|none||none|
|»»» show_info|integer|true|none||none|
|»»» track_id|string|true|none||none|
|»»» pos|integer|true|none||none|
|»»» room_info|null|true|none||none|
|»»» ogv_info|null|true|none||none|
|»»» business_info|null|true|none||none|
|»»» is_stock|integer|true|none||none|
|»»» enable_vt|integer|true|none||none|
|»»» vt_display|string|true|none||none|
|»» side_bar_column|null|true|none||none|
|»» business_card|null|true|none||none|
|»» floor_info|null|true|none||none|
|»» user_feature|null|true|none||none|
|»» preload_expose_pct|integer|true|none||none|
|»» preload_floor_expose_pct|integer|true|none||none|
|»» mid|integer|true|none||none|

## GET 综合热门 (PC)

GET /x/web-interface/popular

### 请求参数

|名称|位置|类型|必选|说明|
|---|---|---|---|---|
|ps|query|string| 否 |none|
|pn|query|string| 否 |none|
|User-Agent|header|string| 否 |none|

> 返回示例

> 200 Response

```json
{
  "code": 0,
  "message": "string",
  "ttl": 0,
  "data": {
    "list": [
      {
        "aid": 0,
        "videos": 0,
        "tid": 0,
        "tname": "string",
        "copyright": 0,
        "pic": "string",
        "title": "string",
        "pubdate": 0,
        "ctime": 0,
        "desc": "string",
        "state": 0,
        "duration": 0,
        "rights": {
          "bp": 0,
          "elec": 0,
          "download": 0,
          "movie": 0,
          "pay": 0,
          "hd5": 0,
          "no_reprint": 0,
          "autoplay": 0,
          "ugc_pay": 0,
          "is_cooperation": 0,
          "ugc_pay_preview": 0,
          "no_background": 0,
          "arc_pay": 0,
          "pay_free_watch": 0
        },
        "owner": {
          "mid": 0,
          "name": "string",
          "face": "string"
        },
        "stat": {
          "aid": 0,
          "view": 0,
          "danmaku": 0,
          "reply": 0,
          "favorite": 0,
          "coin": 0,
          "share": 0,
          "now_rank": 0,
          "his_rank": 0,
          "like": 0,
          "dislike": 0,
          "vt": 0,
          "vv": 0
        },
        "dynamic": "string",
        "cid": 0,
        "dimension": {
          "width": 0,
          "height": 0,
          "rotate": 0
        },
        "short_link_v2": "string",
        "up_from_v2": 0,
        "first_frame": "string",
        "pub_location": "string",
        "bvid": "string",
        "season_type": 0,
        "is_ogv": true,
        "ogv_info": null,
        "enable_vt": 0,
        "rcmd_reason": {
          "content": "string",
          "corner_mark": 0
        },
        "season_id": 0,
        "mission_id": 0
      }
    ],
    "no_more": true
  }
}
```

### 返回结果

|状态码|状态码含义|说明|数据模型|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|成功|Inline|

### 返回数据结构

状态码 **200**

|名称|类型|必选|约束|中文名|说明|
|---|---|---|---|---|---|
|» code|integer|true|none||none|
|» message|string|true|none||none|
|» ttl|integer|true|none||none|
|» data|object|true|none||none|
|»» list|[object]|true|none||none|
|»»» aid|integer|true|none||none|
|»»» videos|integer|true|none||none|
|»»» tid|integer|true|none||none|
|»»» tname|string|true|none||none|
|»»» copyright|integer|true|none||none|
|»»» pic|string|true|none||none|
|»»» title|string|true|none||none|
|»»» pubdate|integer|true|none||none|
|»»» ctime|integer|true|none||none|
|»»» desc|string|true|none||none|
|»»» state|integer|true|none||none|
|»»» duration|integer|true|none||none|
|»»» rights|object|true|none||none|
|»»»» bp|integer|true|none||none|
|»»»» elec|integer|true|none||none|
|»»»» download|integer|true|none||none|
|»»»» movie|integer|true|none||none|
|»»»» pay|integer|true|none||none|
|»»»» hd5|integer|true|none||none|
|»»»» no_reprint|integer|true|none||none|
|»»»» autoplay|integer|true|none||none|
|»»»» ugc_pay|integer|true|none||none|
|»»»» is_cooperation|integer|true|none||none|
|»»»» ugc_pay_preview|integer|true|none||none|
|»»»» no_background|integer|true|none||none|
|»»»» arc_pay|integer|true|none||none|
|»»»» pay_free_watch|integer|true|none||none|
|»»» owner|object|true|none||none|
|»»»» mid|integer|true|none||none|
|»»»» name|string|true|none||none|
|»»»» face|string|true|none||none|
|»»» stat|object|true|none||none|
|»»»» aid|integer|true|none||none|
|»»»» view|integer|true|none||none|
|»»»» danmaku|integer|true|none||none|
|»»»» reply|integer|true|none||none|
|»»»» favorite|integer|true|none||none|
|»»»» coin|integer|true|none||none|
|»»»» share|integer|true|none||none|
|»»»» now_rank|integer|true|none||none|
|»»»» his_rank|integer|true|none||none|
|»»»» like|integer|true|none||none|
|»»»» dislike|integer|true|none||none|
|»»»» vt|integer|true|none||none|
|»»»» vv|integer|true|none||none|
|»»» dynamic|string|true|none||none|
|»»» cid|integer|true|none||none|
|»»» dimension|object|true|none||none|
|»»»» width|integer|true|none||none|
|»»»» height|integer|true|none||none|
|»»»» rotate|integer|true|none||none|
|»»» short_link_v2|string|true|none||none|
|»»» up_from_v2|integer|true|none||none|
|»»» first_frame|string|true|none||none|
|»»» pub_location|string|true|none||none|
|»»» bvid|string|true|none||none|
|»»» season_type|integer|true|none||none|
|»»» is_ogv|boolean|true|none||none|
|»»» ogv_info|null|true|none||none|
|»»» enable_vt|integer|true|none||none|
|»»» rcmd_reason|object|true|none||none|
|»»»» content|string|true|none||none|
|»»»» corner_mark|integer|true|none||none|
|»»» season_id|integer|true|none||none|
|»»» mission_id|integer|true|none||none|
|»» no_more|boolean|true|none||none|

## GET 每周必看 期数列表

GET /x/web-interface/popular/series/list

### 请求参数

|名称|位置|类型|必选|说明|
|---|---|---|---|---|
|User-Agent|header|string| 否 |none|

> 返回示例

> 200 Response

```json
{
  "code": 0,
  "message": "string",
  "ttl": 0,
  "data": {
    "list": [
      {
        "number": 0,
        "subject": "string",
        "status": 0,
        "name": "string"
      }
    ]
  }
}
```

### 返回结果

|状态码|状态码含义|说明|数据模型|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|成功|Inline|

### 返回数据结构

状态码 **200**

|名称|类型|必选|约束|中文名|说明|
|---|---|---|---|---|---|
|» code|integer|true|none||none|
|» message|string|true|none||none|
|» ttl|integer|true|none||none|
|» data|object|true|none||none|
|»» list|[object]|true|none||none|
|»»» number|integer|true|none||none|
|»»» subject|string|true|none||none|
|»»» status|integer|true|none||none|
|»»» name|string|true|none||none|

## GET 每周必看列表

GET /x/web-interface/popular/series/one

### 请求参数

|名称|位置|类型|必选|说明|
|---|---|---|---|---|
|number|query|string| 否 |期数|
|User-Agent|header|string| 否 |none|

> 返回示例

> 200 Response

```json
{
  "code": 0,
  "message": "string",
  "ttl": 0,
  "data": {
    "config": {
      "id": 0,
      "type": "string",
      "number": 0,
      "subject": "string",
      "stime": 0,
      "etime": 0,
      "status": 0,
      "name": "string",
      "label": "string",
      "hint": "string",
      "color": 0,
      "cover": "string",
      "share_title": "string",
      "share_subtitle": "string",
      "media_id": 0
    },
    "reminder": "string",
    "list": [
      {
        "aid": 0,
        "videos": 0,
        "tid": 0,
        "tname": "string",
        "copyright": 0,
        "pic": "string",
        "title": "string",
        "pubdate": 0,
        "ctime": 0,
        "desc": "string",
        "state": 0,
        "duration": 0,
        "mission_id": 0,
        "rights": {
          "bp": 0,
          "elec": 0,
          "download": 0,
          "movie": 0,
          "pay": 0,
          "hd5": 0,
          "no_reprint": 0,
          "autoplay": 0,
          "ugc_pay": 0,
          "is_cooperation": 0,
          "ugc_pay_preview": 0,
          "no_background": 0,
          "arc_pay": 0,
          "pay_free_watch": 0
        },
        "owner": {
          "mid": 0,
          "name": "string",
          "face": "string"
        },
        "stat": {
          "aid": 0,
          "view": 0,
          "danmaku": 0,
          "reply": 0,
          "favorite": 0,
          "coin": 0,
          "share": 0,
          "now_rank": 0,
          "his_rank": 0,
          "like": 0,
          "dislike": 0,
          "vt": 0,
          "vv": 0
        },
        "dynamic": "string",
        "cid": 0,
        "dimension": {
          "width": 0,
          "height": 0,
          "rotate": 0
        },
        "season_id": 0,
        "short_link_v2": "string",
        "first_frame": "string",
        "pub_location": "string",
        "bvid": "string",
        "season_type": 0,
        "is_ogv": true,
        "ogv_info": null,
        "enable_vt": 0,
        "rcmd_reason": "string",
        "up_from_v2": 0
      }
    ]
  }
}
```

### 返回结果

|状态码|状态码含义|说明|数据模型|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|成功|Inline|

### 返回数据结构

状态码 **200**

|名称|类型|必选|约束|中文名|说明|
|---|---|---|---|---|---|
|» code|integer|true|none||none|
|» message|string|true|none||none|
|» ttl|integer|true|none||none|
|» data|object|true|none||none|
|»» config|object|true|none||none|
|»»» id|integer|true|none||none|
|»»» type|string|true|none||none|
|»»» number|integer|true|none||none|
|»»» subject|string|true|none||none|
|»»» stime|integer|true|none||none|
|»»» etime|integer|true|none||none|
|»»» status|integer|true|none||none|
|»»» name|string|true|none||none|
|»»» label|string|true|none||none|
|»»» hint|string|true|none||none|
|»»» color|integer|true|none||none|
|»»» cover|string|true|none||none|
|»»» share_title|string|true|none||none|
|»»» share_subtitle|string|true|none||none|
|»»» media_id|integer|true|none||none|
|»» reminder|string|true|none||none|
|»» list|[object]|true|none||none|
|»»» aid|integer|true|none||none|
|»»» videos|integer|true|none||none|
|»»» tid|integer|true|none||none|
|»»» tname|string|true|none||none|
|»»» copyright|integer|true|none||none|
|»»» pic|string|true|none||none|
|»»» title|string|true|none||none|
|»»» pubdate|integer|true|none||none|
|»»» ctime|integer|true|none||none|
|»»» desc|string|true|none||none|
|»»» state|integer|true|none||none|
|»»» duration|integer|true|none||none|
|»»» mission_id|integer|true|none||none|
|»»» rights|object|true|none||none|
|»»»» bp|integer|true|none||none|
|»»»» elec|integer|true|none||none|
|»»»» download|integer|true|none||none|
|»»»» movie|integer|true|none||none|
|»»»» pay|integer|true|none||none|
|»»»» hd5|integer|true|none||none|
|»»»» no_reprint|integer|true|none||none|
|»»»» autoplay|integer|true|none||none|
|»»»» ugc_pay|integer|true|none||none|
|»»»» is_cooperation|integer|true|none||none|
|»»»» ugc_pay_preview|integer|true|none||none|
|»»»» no_background|integer|true|none||none|
|»»»» arc_pay|integer|true|none||none|
|»»»» pay_free_watch|integer|true|none||none|
|»»» owner|object|true|none||none|
|»»»» mid|integer|true|none||none|
|»»»» name|string|true|none||none|
|»»»» face|string|true|none||none|
|»»» stat|object|true|none||none|
|»»»» aid|integer|true|none||none|
|»»»» view|integer|true|none||none|
|»»»» danmaku|integer|true|none||none|
|»»»» reply|integer|true|none||none|
|»»»» favorite|integer|true|none||none|
|»»»» coin|integer|true|none||none|
|»»»» share|integer|true|none||none|
|»»»» now_rank|integer|true|none||none|
|»»»» his_rank|integer|true|none||none|
|»»»» like|integer|true|none||none|
|»»»» dislike|integer|true|none||none|
|»»»» vt|integer|true|none||none|
|»»»» vv|integer|true|none||none|
|»»» dynamic|string|true|none||none|
|»»» cid|integer|true|none||none|
|»»» dimension|object|true|none||none|
|»»»» width|integer|true|none||none|
|»»»» height|integer|true|none||none|
|»»»» rotate|integer|true|none||none|
|»»» season_id|integer|true|none||none|
|»»» short_link_v2|string|true|none||none|
|»»» first_frame|string|true|none||none|
|»»» pub_location|string|true|none||none|
|»»» bvid|string|true|none||none|
|»»» season_type|integer|true|none||none|
|»»» is_ogv|boolean|true|none||none|
|»»» ogv_info|null|true|none||none|
|»»» enable_vt|integer|true|none||none|
|»»» rcmd_reason|string|true|none||none|
|»»» up_from_v2|integer|true|none||none|

# 直播

## GET 推荐直播间

GET /xlive/web-interface/v1/webMain/getMoreRecList

### 请求参数

|名称|位置|类型|必选|说明|
|---|---|---|---|---|
|platform|query|string| 否 |none|
|User-Agent|header|string| 否 |none|

> 返回示例

> 成功

```json
{
  "code": 0,
  "message": "0",
  "ttl": 1,
  "data": {
    "recommend_room_list": [
      {
        "head_box": null,
        "area_v2_id": 561,
        "area_v2_parent_id": 13,
        "area_v2_name": "游戏赛事",
        "area_v2_parent_name": "赛事",
        "broadcast_type": 0,
        "cover": "http://i0.hdslb.com/bfs/live/03ff530bdadc05f311f4679254f59926c7ba33e8.jpg",
        "link": "/13242892?hotRank=0",
        "online": 109025,
        "pendant_Info": {
          "2": {
            "type": "mobile_index_badge",
            "name": "lottery_anchor_draw",
            "position": 2,
            "text": "天选时刻",
            "bg_color": "#FB9E60",
            "bg_pic": "https://i0.hdslb.com/bfs/live/0cc6f3244063981b21cec7be2692d85f1a6d7792.png",
            "pendant_id": 504,
            "priority": 115,
            "created_at": 1697893364
          }
        },
        "roomid": 13242892,
        "title": "2023和平精英区域对抗赛",
        "uname": "PEL和平精英职业联赛",
        "face": "https://i2.hdslb.com/bfs/face/8ebedf2094784ec20cac1911e7aa97826babce2f.jpg",
        "verify": {
          "role": 3,
          "desc": "PEL和平精英职业联赛官方账号",
          "type": 1
        },
        "uid": 50329337,
        "keyframe": "http://i0.hdslb.com/bfs/live-key-frame/keyframe10212103000013242892358bni.jpg",
        "is_auto_play": 0,
        "head_box_type": 0,
        "flag": 0,
        "session_id": "0cff5ef0438976fa21907cf8176533cd_2474E6A1-00AD-4C7E-A750-37E326545A94",
        "group_id": 1000218,
        "show_callback": "https://live-trace.bilibili.com/xlive/data-interface/v1/index/log?sessionID=0cff5ef0438976fa21907cf8176533cd_2474E6A1-00AD-4C7E-A750-37E326545A94&group_id=1000218&biz=live&event_id=live_card_show&rule_key=&special_id=0&roomid=13242892&parent_id=13&area_id=561&page=0&position=1&platform=web",
        "click_callback": "https://live-trace.bilibili.com/xlive/data-interface/v1/index/log?sessionID=0cff5ef0438976fa21907cf8176533cd_2474E6A1-00AD-4C7E-A750-37E326545A94&group_id=1000218&biz=live&event_id=live_card_click&rule_key=&special_id=0&roomid=13242892&parent_id=13&area_id=561&page=0&position=1&platform=web",
        "special_id": 0,
        "watched_show": {
          "switch": false,
          "num": 109025,
          "text_small": "10.9万",
          "text_large": "10.9万人气",
          "icon": "https://i0.hdslb.com/bfs/live/0b265af1af0a77abc47aa3b8f1a5c0769d8bd23b.png",
          "icon_location": 0,
          "icon_web": "https://i0.hdslb.com/bfs/live/9bb14f7fe0d4988646daf7be7f825314cdd0dbb0.png"
        },
        "is_nft": 0,
        "nft_dmark": "",
        "is_ad": false,
        "ad_transparent_content": null,
        "show_ad_icon": false,
        "status": false,
        "followers": 0
      },
      {
        "head_box": {
          "name": "开播纪念",
          "value": "https://i0.hdslb.com/bfs/live/58ed78db5e536a492173f341fcc928a1149dd38e.png",
          "desc": ""
        },
        "area_v2_id": 236,
        "area_v2_parent_id": 6,
        "area_v2_name": "主机游戏",
        "area_v2_parent_name": "单机游戏",
        "broadcast_type": 0,
        "cover": "http://i0.hdslb.com/bfs/live/new_room_cover/bfd78df24ffeb76726927cf614db2ce9fe5a1798.jpg",
        "link": "/8191310?hotRank=0",
        "online": 162210,
        "pendant_Info": {
          "2": {
            "type": "mobile_index_badge",
            "name": "lottery_anchor_draw",
            "position": 2,
            "text": "天选时刻",
            "bg_color": "#FB9E60",
            "bg_pic": "https://i0.hdslb.com/bfs/live/0cc6f3244063981b21cec7be2692d85f1a6d7792.png",
            "pendant_id": 504,
            "priority": 115,
            "created_at": 1697893641
          }
        },
        "roomid": 8191310,
        "title": "摄像头 四周年庆！",
        "uname": "_瑞德_",
        "face": "https://i2.hdslb.com/bfs/face/36d0dc4b436ebce35cb5317bac585d884751ff62.jpg",
        "verify": {
          "role": 7,
          "desc": "bilibili 直播高能主播",
          "type": 0
        },
        "uid": 1446806,
        "keyframe": "http://i0.hdslb.com/bfs/live-key-frame/keyframe102121010000081913101l7p3p.jpg",
        "is_auto_play": 1,
        "head_box_type": 1,
        "flag": 0,
        "session_id": "0cff5ef0438976fa21907cf8176533cd_B368ACE1-EE4F-455D-B4AE-1963857A930B",
        "group_id": 1000228,
        "show_callback": "https://live-trace.bilibili.com/xlive/data-interface/v1/index/log?sessionID=0cff5ef0438976fa21907cf8176533cd_B368ACE1-EE4F-455D-B4AE-1963857A930B&group_id=1000228&biz=live&event_id=live_card_show&rule_key=&special_id=0&roomid=8191310&parent_id=6&area_id=236&page=0&position=2&platform=web",
        "click_callback": "https://live-trace.bilibili.com/xlive/data-interface/v1/index/log?sessionID=0cff5ef0438976fa21907cf8176533cd_B368ACE1-EE4F-455D-B4AE-1963857A930B&group_id=1000228&biz=live&event_id=live_card_click&rule_key=&special_id=0&roomid=8191310&parent_id=6&area_id=236&page=0&position=2&platform=web",
        "special_id": 0,
        "watched_show": {
          "switch": true,
          "num": 1518,
          "text_small": "1518",
          "text_large": "1518人看过",
          "icon": "https://i0.hdslb.com/bfs/live/a725a9e61242ef44d764ac911691a7ce07f36c1d.png",
          "icon_location": 0,
          "icon_web": "https://i0.hdslb.com/bfs/live/8d9d0f33ef8bf6f308742752d13dd0df731df19c.png"
        },
        "is_nft": 0,
        "nft_dmark": "",
        "is_ad": false,
        "ad_transparent_content": null,
        "show_ad_icon": false,
        "status": false,
        "followers": 0
      },
      {
        "head_box": {
          "name": "果香四溢",
          "value": "https://i0.hdslb.com/bfs/live/63cb3624e2f6a3990098e2be68a3fcd1f0306c14.png",
          "desc": ""
        },
        "area_v2_id": 818,
        "area_v2_parent_id": 14,
        "area_v2_name": "交友",
        "area_v2_parent_name": "聊天室",
        "broadcast_type": 1,
        "cover": "http://i0.hdslb.com/bfs/live/new_room_cover/38e5195739c99fde3f45e1d3b029069fa6736c48.jpg",
        "link": "/30864851?hotRank=0",
        "online": 39593,
        "pendant_Info": {},
        "roomid": 30864851,
        "title": "四川女娃儿真的很温柔~",
        "uname": "水星记-待冠名",
        "face": "https://i0.hdslb.com/bfs/face/8e66da494e6ecef9e60fb2bb7a05f4a7d723c5e3.jpg",
        "verify": {
          "role": 0,
          "desc": "",
          "type": -1
        },
        "uid": 3546387142674753,
        "keyframe": "http://i0.hdslb.com/bfs/live-key-frame/keyframe10212106000030864851ndtit8.jpg",
        "is_auto_play": 0,
        "head_box_type": 1,
        "flag": 0,
        "session_id": "0cff5ef0438976fa21907cf8176533cd_34C5B9A9-A19B-43DC-86D9-B0708D8632CE",
        "group_id": 1000228,
        "show_callback": "https://live-trace.bilibili.com/xlive/data-interface/v1/index/log?sessionID=0cff5ef0438976fa21907cf8176533cd_34C5B9A9-A19B-43DC-86D9-B0708D8632CE&group_id=1000228&biz=live&event_id=live_card_show&rule_key=&special_id=0&roomid=30864851&parent_id=14&area_id=818&page=0&position=3&platform=web",
        "click_callback": "https://live-trace.bilibili.com/xlive/data-interface/v1/index/log?sessionID=0cff5ef0438976fa21907cf8176533cd_34C5B9A9-A19B-43DC-86D9-B0708D8632CE&group_id=1000228&biz=live&event_id=live_card_click&rule_key=&special_id=0&roomid=30864851&parent_id=14&area_id=818&page=0&position=3&platform=web",
        "special_id": 0,
        "watched_show": {
          "switch": true,
          "num": 289,
          "text_small": "289",
          "text_large": "289人看过",
          "icon": "https://i0.hdslb.com/bfs/live/a725a9e61242ef44d764ac911691a7ce07f36c1d.png",
          "icon_location": 0,
          "icon_web": "https://i0.hdslb.com/bfs/live/8d9d0f33ef8bf6f308742752d13dd0df731df19c.png"
        },
        "is_nft": 0,
        "nft_dmark": "",
        "is_ad": false,
        "ad_transparent_content": null,
        "show_ad_icon": false,
        "status": false,
        "followers": 0
      },
      {
        "head_box": {
          "name": "果香四溢",
          "value": "https://i0.hdslb.com/bfs/live/63cb3624e2f6a3990098e2be68a3fcd1f0306c14.png",
          "desc": ""
        },
        "area_v2_id": 145,
        "area_v2_parent_id": 1,
        "area_v2_name": "视频聊天",
        "area_v2_parent_name": "娱乐",
        "broadcast_type": 1,
        "cover": "http://i0.hdslb.com/bfs/live/user_cover/acec3cf862131562557810a8236fa6ab86795c1f.jpg",
        "link": "/31100414?hotRank=0",
        "online": 14668,
        "pendant_Info": {},
        "roomid": 31100414,
        "title": "67岁没有做过保养自信的女人最美",
        "uname": "扔掉哈密瓜",
        "face": "https://i2.hdslb.com/bfs/face/057ed582ab98dd3b44d8e37d4ae5c6f0b3def835.jpg",
        "verify": {
          "role": 0,
          "desc": "",
          "type": -1
        },
        "uid": 3546563764816769,
        "keyframe": "http://i0.hdslb.com/bfs/live-key-frame/keyframe10212100000031100414id0p8d.jpg",
        "is_auto_play": 0,
        "head_box_type": 1,
        "flag": 0,
        "session_id": "0cff5ef0438976fa21907cf8176533cd_DBAACC14-B2D4-4ED8-AE9D-A9D3B452BD0A",
        "group_id": 1000228,
        "show_callback": "https://live-trace.bilibili.com/xlive/data-interface/v1/index/log?sessionID=0cff5ef0438976fa21907cf8176533cd_DBAACC14-B2D4-4ED8-AE9D-A9D3B452BD0A&group_id=1000228&biz=live&event_id=live_card_show&rule_key=&special_id=0&roomid=31100414&parent_id=1&area_id=145&page=0&position=4&platform=web",
        "click_callback": "https://live-trace.bilibili.com/xlive/data-interface/v1/index/log?sessionID=0cff5ef0438976fa21907cf8176533cd_DBAACC14-B2D4-4ED8-AE9D-A9D3B452BD0A&group_id=1000228&biz=live&event_id=live_card_click&rule_key=&special_id=0&roomid=31100414&parent_id=1&area_id=145&page=0&position=4&platform=web",
        "special_id": 0,
        "watched_show": {
          "switch": true,
          "num": 1158,
          "text_small": "1158",
          "text_large": "1158人看过",
          "icon": "https://i0.hdslb.com/bfs/live/a725a9e61242ef44d764ac911691a7ce07f36c1d.png",
          "icon_location": 0,
          "icon_web": "https://i0.hdslb.com/bfs/live/8d9d0f33ef8bf6f308742752d13dd0df731df19c.png"
        },
        "is_nft": 0,
        "nft_dmark": "",
        "is_ad": false,
        "ad_transparent_content": null,
        "show_ad_icon": false,
        "status": false,
        "followers": 0
      },
      {
        "head_box": {
          "name": "S38钢之勇者",
          "value": "https://i0.hdslb.com/bfs/live/0751279ea7713af400b8e4b1a43dbb22af33e920.png",
          "desc": ""
        },
        "area_v2_id": 805,
        "area_v2_parent_id": 3,
        "area_v2_name": "闪耀！优俊少女",
        "area_v2_parent_name": "手游",
        "broadcast_type": 0,
        "cover": "http://i0.hdslb.com/bfs/live/new_room_cover/a2f598566fdf8d4fe6da34ea9700659086229e44.jpg",
        "link": "/30741407?hotRank=0",
        "online": 12458,
        "pendant_Info": {},
        "roomid": 30741407,
        "title": "【闪！】合宿0彩仙人！有问必答！",
        "uname": "特雷森一年生",
        "face": "https://i0.hdslb.com/bfs/face/c37f4e4b1878601cbb5f1e0584501aa654cd8bf5.jpg",
        "verify": {
          "role": 0,
          "desc": "",
          "type": -1
        },
        "uid": 3546373368580317,
        "keyframe": "http://i0.hdslb.com/bfs/live-key-frame/keyframe10212100000030741407qf45dn.jpg",
        "is_auto_play": 1,
        "head_box_type": 1,
        "flag": 0,
        "session_id": "0cff5ef0438976fa21907cf8176533cd_73CB8E07-7178-48F9-AD89-090AD071B26D",
        "group_id": 1000228,
        "show_callback": "https://live-trace.bilibili.com/xlive/data-interface/v1/index/log?sessionID=0cff5ef0438976fa21907cf8176533cd_73CB8E07-7178-48F9-AD89-090AD071B26D&group_id=1000228&biz=live&event_id=live_card_show&rule_key=&special_id=0&roomid=30741407&parent_id=3&area_id=805&page=0&position=5&platform=web",
        "click_callback": "https://live-trace.bilibili.com/xlive/data-interface/v1/index/log?sessionID=0cff5ef0438976fa21907cf8176533cd_73CB8E07-7178-48F9-AD89-090AD071B26D&group_id=1000228&biz=live&event_id=live_card_click&rule_key=&special_id=0&roomid=30741407&parent_id=3&area_id=805&page=0&position=5&platform=web",
        "special_id": 0,
        "watched_show": {
          "switch": true,
          "num": 827,
          "text_small": "827",
          "text_large": "827人看过",
          "icon": "https://i0.hdslb.com/bfs/live/a725a9e61242ef44d764ac911691a7ce07f36c1d.png",
          "icon_location": 0,
          "icon_web": "https://i0.hdslb.com/bfs/live/8d9d0f33ef8bf6f308742752d13dd0df731df19c.png"
        },
        "is_nft": 0,
        "nft_dmark": "",
        "is_ad": false,
        "ad_transparent_content": null,
        "show_ad_icon": false,
        "status": false,
        "followers": 0
      },
      {
        "head_box": null,
        "area_v2_id": 236,
        "area_v2_parent_id": 6,
        "area_v2_name": "主机游戏",
        "area_v2_parent_name": "单机游戏",
        "broadcast_type": 0,
        "cover": "http://i0.hdslb.com/bfs/live/new_room_cover/14d45a323e31105b576cf47b5c241141441ffac5.jpg",
        "link": "/4332855?hotRank=0",
        "online": 8967,
        "pendant_Info": {},
        "roomid": 4332855,
        "title": "种田基建还能突突突",
        "uname": "风吻无痕",
        "face": "http://i1.hdslb.com/bfs/face/382440c879e8d8629b21e08f18aefd38e911b7db.jpg",
        "verify": {
          "role": 0,
          "desc": "",
          "type": -1
        },
        "uid": 111216342,
        "keyframe": "http://i0.hdslb.com/bfs/live-key-frame/keyframe10212106000004332855qq6m00.jpg",
        "is_auto_play": 1,
        "head_box_type": 0,
        "flag": 0,
        "session_id": "0cff5ef0438976fa21907cf8176533cd_3F165ED1-3C47-416C-841C-57CAF7276847",
        "group_id": 1000228,
        "show_callback": "https://live-trace.bilibili.com/xlive/data-interface/v1/index/log?sessionID=0cff5ef0438976fa21907cf8176533cd_3F165ED1-3C47-416C-841C-57CAF7276847&group_id=1000228&biz=live&event_id=live_card_show&rule_key=&special_id=0&roomid=4332855&parent_id=6&area_id=236&page=0&position=6&platform=web",
        "click_callback": "https://live-trace.bilibili.com/xlive/data-interface/v1/index/log?sessionID=0cff5ef0438976fa21907cf8176533cd_3F165ED1-3C47-416C-841C-57CAF7276847&group_id=1000228&biz=live&event_id=live_card_click&rule_key=&special_id=0&roomid=4332855&parent_id=6&area_id=236&page=0&position=6&platform=web",
        "special_id": 0,
        "watched_show": {
          "switch": true,
          "num": 189,
          "text_small": "189",
          "text_large": "189人看过",
          "icon": "https://i0.hdslb.com/bfs/live/a725a9e61242ef44d764ac911691a7ce07f36c1d.png",
          "icon_location": 0,
          "icon_web": "https://i0.hdslb.com/bfs/live/8d9d0f33ef8bf6f308742752d13dd0df731df19c.png"
        },
        "is_nft": 0,
        "nft_dmark": "",
        "is_ad": false,
        "ad_transparent_content": null,
        "show_ad_icon": false,
        "status": false,
        "followers": 0
      },
      {
        "head_box": {
          "name": "果香四溢",
          "value": "https://i0.hdslb.com/bfs/live/63cb3624e2f6a3990098e2be68a3fcd1f0306c14.png",
          "desc": ""
        },
        "area_v2_id": 329,
        "area_v2_parent_id": 2,
        "area_v2_name": "无畏契约",
        "area_v2_parent_name": "网游",
        "broadcast_type": 0,
        "cover": "http://i0.hdslb.com/bfs/live/new_room_cover/b07eac4c9dd85bd094ab2313fd0803194d874344.jpg",
        "link": "/23535840?hotRank=0",
        "online": 8931,
        "pendant_Info": {},
        "roomid": 23535840,
        "title": "【有车位】直播还债第一天~",
        "uname": "阿酒不想努力了",
        "face": "https://i2.hdslb.com/bfs/face/2e7e2ebbd5af2cc5f74b8aea5c475bd4fbae8bd1.jpg",
        "verify": {
          "role": 0,
          "desc": "",
          "type": -1
        },
        "uid": 388092833,
        "keyframe": "http://i0.hdslb.com/bfs/live-key-frame/keyframe10212103000023535840xj5gxa.jpg",
        "is_auto_play": 1,
        "head_box_type": 1,
        "flag": 0,
        "session_id": "0cff5ef0438976fa21907cf8176533cd_EF28A0BE-6827-41CC-A6CE-1C9225B3C5AE",
        "group_id": 1000228,
        "show_callback": "https://live-trace.bilibili.com/xlive/data-interface/v1/index/log?sessionID=0cff5ef0438976fa21907cf8176533cd_EF28A0BE-6827-41CC-A6CE-1C9225B3C5AE&group_id=1000228&biz=live&event_id=live_card_show&rule_key=&special_id=0&roomid=23535840&parent_id=2&area_id=329&page=0&position=7&platform=web",
        "click_callback": "https://live-trace.bilibili.com/xlive/data-interface/v1/index/log?sessionID=0cff5ef0438976fa21907cf8176533cd_EF28A0BE-6827-41CC-A6CE-1C9225B3C5AE&group_id=1000228&biz=live&event_id=live_card_click&rule_key=&special_id=0&roomid=23535840&parent_id=2&area_id=329&page=0&position=7&platform=web",
        "special_id": 0,
        "watched_show": {
          "switch": true,
          "num": 27,
          "text_small": "27",
          "text_large": "27人看过",
          "icon": "https://i0.hdslb.com/bfs/live/a725a9e61242ef44d764ac911691a7ce07f36c1d.png",
          "icon_location": 0,
          "icon_web": "https://i0.hdslb.com/bfs/live/8d9d0f33ef8bf6f308742752d13dd0df731df19c.png"
        },
        "is_nft": 0,
        "nft_dmark": "",
        "is_ad": false,
        "ad_transparent_content": null,
        "show_ad_icon": false,
        "status": false,
        "followers": 0
      },
      {
        "head_box": {
          "name": "果香四溢",
          "value": "https://i0.hdslb.com/bfs/live/63cb3624e2f6a3990098e2be68a3fcd1f0306c14.png",
          "desc": ""
        },
        "area_v2_id": 744,
        "area_v2_parent_id": 9,
        "area_v2_name": "虚拟Singer",
        "area_v2_parent_name": "虚拟主播",
        "broadcast_type": 0,
        "cover": "http://i0.hdslb.com/bfs/live/new_room_cover/74e5136ce51c75276e4fe0961655124000150d7b.jpg",
        "link": "/5432726?hotRank=0",
        "online": 31824,
        "pendant_Info": {},
        "roomid": 5432726,
        "title": "一岁啦！一周年大猛狼w",
        "uname": "凯凯KaKai",
        "face": "https://i1.hdslb.com/bfs/face/1118c673cc4b14ed0f7c59c6dcb4cd6fb7c4c8cc.jpg",
        "verify": {
          "role": 0,
          "desc": "",
          "type": -1
        },
        "uid": 195469924,
        "keyframe": "http://i0.hdslb.com/bfs/live-key-frame/keyframe10212106000005432726oohr10.jpg",
        "is_auto_play": 0,
        "head_box_type": 1,
        "flag": 0,
        "session_id": "0cff5ef0438976fa21907cf8176533cd_E24C0A60-D4F1-4FF3-A2E2-E2FC4E0DAE73",
        "group_id": 1000228,
        "show_callback": "https://live-trace.bilibili.com/xlive/data-interface/v1/index/log?sessionID=0cff5ef0438976fa21907cf8176533cd_E24C0A60-D4F1-4FF3-A2E2-E2FC4E0DAE73&group_id=1000228&biz=live&event_id=live_card_show&rule_key=&special_id=0&roomid=5432726&parent_id=9&area_id=744&page=0&position=8&platform=web",
        "click_callback": "https://live-trace.bilibili.com/xlive/data-interface/v1/index/log?sessionID=0cff5ef0438976fa21907cf8176533cd_E24C0A60-D4F1-4FF3-A2E2-E2FC4E0DAE73&group_id=1000228&biz=live&event_id=live_card_click&rule_key=&special_id=0&roomid=5432726&parent_id=9&area_id=744&page=0&position=8&platform=web",
        "special_id": 0,
        "watched_show": {
          "switch": true,
          "num": 444,
          "text_small": "444",
          "text_large": "444人看过",
          "icon": "https://i0.hdslb.com/bfs/live/a725a9e61242ef44d764ac911691a7ce07f36c1d.png",
          "icon_location": 0,
          "icon_web": "https://i0.hdslb.com/bfs/live/8d9d0f33ef8bf6f308742752d13dd0df731df19c.png"
        },
        "is_nft": 0,
        "nft_dmark": "",
        "is_ad": false,
        "ad_transparent_content": null,
        "show_ad_icon": false,
        "status": false,
        "followers": 0
      },
      {
        "head_box": {
          "name": "爱意满满",
          "value": "https://i0.hdslb.com/bfs/live/428d5ea45c46c588d405c74b0331c6249c1b212e.png",
          "desc": ""
        },
        "area_v2_id": 89,
        "area_v2_parent_id": 2,
        "area_v2_name": "CS:GO",
        "area_v2_parent_name": "网游",
        "broadcast_type": 0,
        "cover": "http://i0.hdslb.com/bfs/live/new_room_cover/dd057392ae600e45e82ea0699d34b729135a2aff.jpg",
        "link": "/10124752?hotRank=0",
        "online": 21516,
        "pendant_Info": {},
        "roomid": 10124752,
        "title": "桃心狙击手",
        "uname": "川岛智",
        "face": "https://i0.hdslb.com/bfs/face/f07ed901fadd729c908b13bf73a6761c4c65c50a.jpg",
        "verify": {
          "role": 7,
          "desc": "bilibili 直播高能主播",
          "type": 0
        },
        "uid": 255928137,
        "keyframe": "http://i0.hdslb.com/bfs/live-key-frame/keyframe102121020000101247529oosgf.jpg",
        "is_auto_play": 1,
        "head_box_type": 1,
        "flag": 0,
        "session_id": "0cff5ef0438976fa21907cf8176533cd_BE701760-EAAA-4F91-A6BD-3EC4C8A0533F",
        "group_id": 1000228,
        "show_callback": "https://live-trace.bilibili.com/xlive/data-interface/v1/index/log?sessionID=0cff5ef0438976fa21907cf8176533cd_BE701760-EAAA-4F91-A6BD-3EC4C8A0533F&group_id=1000228&biz=live&event_id=live_card_show&rule_key=&special_id=0&roomid=10124752&parent_id=2&area_id=89&page=0&position=9&platform=web",
        "click_callback": "https://live-trace.bilibili.com/xlive/data-interface/v1/index/log?sessionID=0cff5ef0438976fa21907cf8176533cd_BE701760-EAAA-4F91-A6BD-3EC4C8A0533F&group_id=1000228&biz=live&event_id=live_card_click&rule_key=&special_id=0&roomid=10124752&parent_id=2&area_id=89&page=0&position=9&platform=web",
        "special_id": 0,
        "watched_show": {
          "switch": true,
          "num": 839,
          "text_small": "839",
          "text_large": "839人看过",
          "icon": "https://i0.hdslb.com/bfs/live/a725a9e61242ef44d764ac911691a7ce07f36c1d.png",
          "icon_location": 0,
          "icon_web": "https://i0.hdslb.com/bfs/live/8d9d0f33ef8bf6f308742752d13dd0df731df19c.png"
        },
        "is_nft": 0,
        "nft_dmark": "",
        "is_ad": false,
        "ad_transparent_content": null,
        "show_ad_icon": false,
        "status": false,
        "followers": 0
      },
      {
        "head_box": {
          "name": "果香四溢",
          "value": "https://i0.hdslb.com/bfs/live/63cb3624e2f6a3990098e2be68a3fcd1f0306c14.png",
          "desc": ""
        },
        "area_v2_id": 87,
        "area_v2_parent_id": 2,
        "area_v2_name": "守望先锋",
        "area_v2_parent_name": "网游",
        "broadcast_type": 0,
        "cover": "http://i0.hdslb.com/bfs/live/new_room_cover/e50a9409a2b5aea053f67f437467665f4aeff696.jpg",
        "link": "/24105866?hotRank=0",
        "online": 1903,
        "pendant_Info": {},
        "roomid": 24105866,
        "title": "哪有不疯的呢",
        "uname": "沈星挽Van",
        "face": "https://i0.hdslb.com/bfs/face/3b66d14db5bb72f79d6598dd0787afc62fb04623.jpg",
        "verify": {
          "role": 0,
          "desc": "",
          "type": -1
        },
        "uid": 323974332,
        "keyframe": "http://i0.hdslb.com/bfs/live-key-frame/keyframe10212100000024105866bd4d53.jpg",
        "is_auto_play": 1,
        "head_box_type": 1,
        "flag": 0,
        "session_id": "0cff5ef0438976fa21907cf8176533cd_3CD8A99F-6054-493E-B200-17E27D3730D5",
        "group_id": 1000218,
        "show_callback": "https://live-trace.bilibili.com/xlive/data-interface/v1/index/log?sessionID=0cff5ef0438976fa21907cf8176533cd_3CD8A99F-6054-493E-B200-17E27D3730D5&group_id=1000218&biz=live&event_id=live_card_show&rule_key=&special_id=0&roomid=24105866&parent_id=2&area_id=87&page=0&position=10&platform=web",
        "click_callback": "https://live-trace.bilibili.com/xlive/data-interface/v1/index/log?sessionID=0cff5ef0438976fa21907cf8176533cd_3CD8A99F-6054-493E-B200-17E27D3730D5&group_id=1000218&biz=live&event_id=live_card_click&rule_key=&special_id=0&roomid=24105866&parent_id=2&area_id=87&page=0&position=10&platform=web",
        "special_id": 0,
        "watched_show": {
          "switch": true,
          "num": 122,
          "text_small": "122",
          "text_large": "122人看过",
          "icon": "https://i0.hdslb.com/bfs/live/a725a9e61242ef44d764ac911691a7ce07f36c1d.png",
          "icon_location": 0,
          "icon_web": "https://i0.hdslb.com/bfs/live/8d9d0f33ef8bf6f308742752d13dd0df731df19c.png"
        },
        "is_nft": 0,
        "nft_dmark": "",
        "is_ad": false,
        "ad_transparent_content": null,
        "show_ad_icon": false,
        "status": false,
        "followers": 0
      },
      {
        "head_box": {
          "name": "果香四溢",
          "value": "https://i0.hdslb.com/bfs/live/63cb3624e2f6a3990098e2be68a3fcd1f0306c14.png",
          "desc": ""
        },
        "area_v2_id": 817,
        "area_v2_parent_id": 5,
        "area_v2_name": "甜宠电台",
        "area_v2_parent_name": "电台",
        "broadcast_type": 0,
        "cover": "http://i0.hdslb.com/bfs/live/new_room_cover/1b449e260c8a513f673450a8233f870c04fa5509.jpg",
        "link": "/30948020?hotRank=0",
        "online": 18746,
        "pendant_Info": {},
        "roomid": 30948020,
        "title": "广东顶级甜妹",
        "uname": "小酒甜甜酱_-_",
        "face": "https://i1.hdslb.com/bfs/face/4a234d561e1f9352e7d24725a3410f8a7a189ba0.jpg",
        "verify": {
          "role": 0,
          "desc": "",
          "type": -1
        },
        "uid": 3546392920328830,
        "keyframe": "http://i0.hdslb.com/bfs/live-key-frame/keyframe10212106000030948020nf351w.jpg",
        "is_auto_play": 0,
        "head_box_type": 1,
        "flag": 0,
        "session_id": "0cff5ef0438976fa21907cf8176533cd_5CA909CD-F6DF-4A87-84EE-3629DE5B6292",
        "group_id": 1000228,
        "show_callback": "https://live-trace.bilibili.com/xlive/data-interface/v1/index/log?sessionID=0cff5ef0438976fa21907cf8176533cd_5CA909CD-F6DF-4A87-84EE-3629DE5B6292&group_id=1000228&biz=live&event_id=live_card_show&rule_key=&special_id=0&roomid=30948020&parent_id=5&area_id=817&page=0&position=11&platform=web",
        "click_callback": "https://live-trace.bilibili.com/xlive/data-interface/v1/index/log?sessionID=0cff5ef0438976fa21907cf8176533cd_5CA909CD-F6DF-4A87-84EE-3629DE5B6292&group_id=1000228&biz=live&event_id=live_card_click&rule_key=&special_id=0&roomid=30948020&parent_id=5&area_id=817&page=0&position=11&platform=web",
        "special_id": 0,
        "watched_show": {
          "switch": true,
          "num": 614,
          "text_small": "614",
          "text_large": "614人看过",
          "icon": "https://i0.hdslb.com/bfs/live/a725a9e61242ef44d764ac911691a7ce07f36c1d.png",
          "icon_location": 0,
          "icon_web": "https://i0.hdslb.com/bfs/live/8d9d0f33ef8bf6f308742752d13dd0df731df19c.png"
        },
        "is_nft": 0,
        "nft_dmark": "",
        "is_ad": false,
        "ad_transparent_content": null,
        "show_ad_icon": false,
        "status": false,
        "followers": 0
      },
      {
        "head_box": {
          "name": "果香四溢",
          "value": "https://i0.hdslb.com/bfs/live/63cb3624e2f6a3990098e2be68a3fcd1f0306c14.png",
          "desc": ""
        },
        "area_v2_id": 371,
        "area_v2_parent_id": 9,
        "area_v2_name": "虚拟日常",
        "area_v2_parent_name": "虚拟主播",
        "broadcast_type": 0,
        "cover": "http://i0.hdslb.com/bfs/live/new_room_cover/d1e1b6966cf4bd477fe035e7ef45a27d731a5bab.jpg",
        "link": "/26763749?hotRank=0",
        "online": 14430,
        "pendant_Info": {
          "2": {
            "type": "mobile_index_badge",
            "name": "粉丝会",
            "position": 2,
            "text": "粉丝会",
            "bg_color": "#FB9E60",
            "bg_pic": "http://i0.hdslb.com/bfs/live/1b8e99563760278114da58d8aa92b68260f99ff4.png",
            "pendant_id": 1260,
            "priority": 100,
            "created_at": 1697816703
          }
        },
        "roomid": 26763749,
        "title": "夜夜的第一次连麦回！",
        "uname": "神山夜夜",
        "face": "https://i2.hdslb.com/bfs/face/1f9a67a76d705fa262ffcae32fc7e32ef20532fb.jpg",
        "verify": {
          "role": 0,
          "desc": "",
          "type": -1
        },
        "uid": 651143714,
        "keyframe": "http://i0.hdslb.com/bfs/live-key-frame/keyframe10212106000026763749df00hz.jpg",
        "is_auto_play": 0,
        "head_box_type": 1,
        "flag": 0,
        "session_id": "0cff5ef0438976fa21907cf8176533cd_335A8A23-C362-4DCE-9B94-D0744A5BF4F9",
        "group_id": 1000228,
        "show_callback": "https://live-trace.bilibili.com/xlive/data-interface/v1/index/log?sessionID=0cff5ef0438976fa21907cf8176533cd_335A8A23-C362-4DCE-9B94-D0744A5BF4F9&group_id=1000228&biz=live&event_id=live_card_show&rule_key=&special_id=0&roomid=26763749&parent_id=9&area_id=371&page=0&position=12&platform=web",
        "click_callback": "https://live-trace.bilibili.com/xlive/data-interface/v1/index/log?sessionID=0cff5ef0438976fa21907cf8176533cd_335A8A23-C362-4DCE-9B94-D0744A5BF4F9&group_id=1000228&biz=live&event_id=live_card_click&rule_key=&special_id=0&roomid=26763749&parent_id=9&area_id=371&page=0&position=12&platform=web",
        "special_id": 0,
        "watched_show": {
          "switch": true,
          "num": 138,
          "text_small": "138",
          "text_large": "138人看过",
          "icon": "https://i0.hdslb.com/bfs/live/a725a9e61242ef44d764ac911691a7ce07f36c1d.png",
          "icon_location": 0,
          "icon_web": "https://i0.hdslb.com/bfs/live/8d9d0f33ef8bf6f308742752d13dd0df731df19c.png"
        },
        "is_nft": 0,
        "nft_dmark": "",
        "is_ad": false,
        "ad_transparent_content": null,
        "show_ad_icon": false,
        "status": false,
        "followers": 0
      }
    ]
  }
}
```

### 返回结果

|状态码|状态码含义|说明|数据模型|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|成功|Inline|

### 返回数据结构

# 鉴权

## GET 生成登录二维码

GET /x/passport-login/web/qrcode/generate

### 请求参数

|名称|位置|类型|必选|说明|
|---|---|---|---|---|
|User-Agent|header|string| 否 |none|

> 返回示例

> 成功

```json
{
  "code": 0,
  "message": "0",
  "ttl": 1,
  "data": {
    "url": "https://passport.bilibili.com/h5-app/passport/login/scan?navhide=1&qrcode_key=53468a49e16291b8638e01b695631f22&from=",
    "qrcode_key": "53468a49e16291b8638e01b695631f22"
  }
}
```

### 返回结果

|状态码|状态码含义|说明|数据模型|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|成功|Inline|

### 返回数据结构

## GET 获取扫描二维码状态

GET /x/passport-login/web/qrcode/poll

### 请求参数

|名称|位置|类型|必选|说明|
|---|---|---|---|---|
|qrcode_key|query|string| 否 |二维码key|
|source|query|string| 否 |来源|
|User-Agent|header|string| 否 |none|

> 返回示例

> 成功

```json
{
  "code": 0,
  "message": "0",
  "ttl": 1,
  "data": {
    "url": "",
    "refresh_token": "",
    "timestamp": 0,
    "code": 86101,
    "message": "未扫码"
  }
}
```

### 返回结果

|状态码|状态码含义|说明|数据模型|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|成功|Inline|

### 返回数据结构

状态码 **200**

|名称|类型|必选|约束|中文名|说明|
|---|---|---|---|---|---|
|» code|integer|true|none||none|
|» message|string|true|none||none|
|» ttl|integer|true|none||none|
|» data|object|true|none||none|
|»» url|string|true|none||none|
|»» refresh_token|string|true|none||none|
|»» timestamp|integer|true|none||none|
|»» code|integer|true|none||none|
|»» message|string|true|none||none|

## POST 退出登录

POST /login/exit/v2

> Body 请求参数

```yaml
biliCSRF: xxxxxxxxx
gourl: https://www.bilibili.com/

```

### 请求参数

|名称|位置|类型|必选|说明|
|---|---|---|---|---|
|User-Agent|header|string| 否 |none|
|body|body|object| 否 |none|
|» biliCSRF|body|string| 否 |对应cookie中的bili_jct|
|» gourl|body|string| 否 |重定向路由|

> 返回示例

> 200 Response

### 返回结果

|状态码|状态码含义|说明|数据模型|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|成功|Inline|

### 返回数据结构

# 视频

## GET 在线人数

GET /x/player/online/total

### 请求参数

|名称|位置|类型|必选|说明|
|---|---|---|---|---|
|aid|query|string| 否 |none|
|cid|query|string| 否 |none|
|bvid|query|string| 否 |none|
|User-Agent|header|string| 否 |none|

> 返回示例

> 200 Response

```json
{}
```

### 返回结果

|状态码|状态码含义|说明|数据模型|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|成功|Inline|

### 返回数据结构

# 界面

## GET 导航栏数据

GET /x/web-interface/nav

### 请求参数

|名称|位置|类型|必选|说明|
|---|---|---|---|---|
|User-Agent|header|string| 否 |none|

> 返回示例

> 成功

```json
{
  "code": 0,
  "message": "0",
  "ttl": 1,
  "data": {
    "isLogin": true,
    "email_verified": 0,
    "face": "https://i1.hdslb.com/bfs/face/b4e08d394ace1dda4fa731f105bf7efe5a3b6ec3.jpg",
    "face_nft": 0,
    "face_nft_type": 0,
    "level_info": {
      "current_level": 5,
      "current_min": 10800,
      "current_exp": 13515,
      "next_exp": 28800
    },
    "mid": 554384020,
    "mobile_verified": 1,
    "money": 733,
    "moral": 70,
    "official": {
      "role": 0,
      "title": "",
      "desc": "",
      "type": -1
    },
    "officialVerify": {
      "type": -1,
      "desc": ""
    },
    "pendant": {
      "pid": 0,
      "name": "",
      "image": "",
      "expire": 0,
      "image_enhance": "",
      "image_enhance_frame": ""
    },
    "scores": 0,
    "uname": "a14n",
    "vipDueDate": 1658937600000,
    "vipStatus": 0,
    "vipType": 1,
    "vip_pay_type": 0,
    "vip_theme_type": 0,
    "vip_label": {
      "path": "",
      "text": "",
      "label_theme": "",
      "text_color": "",
      "bg_style": 0,
      "bg_color": "",
      "border_color": "",
      "use_img_label": true,
      "img_label_uri_hans": "",
      "img_label_uri_hant": "",
      "img_label_uri_hans_static": "https://i0.hdslb.com/bfs/vip/d7b702ef65a976b20ed854cbd04cb9e27341bb79.png",
      "img_label_uri_hant_static": "https://i0.hdslb.com/bfs/activity-plat/static/20220614/e369244d0b14644f5e1a06431e22a4d5/KJunwh19T5.png"
    },
    "vip_avatar_subscript": 0,
    "vip_nickname_color": "",
    "vip": {
      "type": 1,
      "status": 0,
      "due_date": 1658937600000,
      "vip_pay_type": 0,
      "theme_type": 0,
      "label": {
        "path": "",
        "text": "",
        "label_theme": "",
        "text_color": "",
        "bg_style": 0,
        "bg_color": "",
        "border_color": "",
        "use_img_label": true,
        "img_label_uri_hans": "",
        "img_label_uri_hant": "",
        "img_label_uri_hans_static": "https://i0.hdslb.com/bfs/vip/d7b702ef65a976b20ed854cbd04cb9e27341bb79.png",
        "img_label_uri_hant_static": "https://i0.hdslb.com/bfs/activity-plat/static/20220614/e369244d0b14644f5e1a06431e22a4d5/KJunwh19T5.png"
      },
      "avatar_subscript": 0,
      "nickname_color": "",
      "role": 0,
      "avatar_subscript_url": "",
      "tv_vip_status": 0,
      "tv_vip_pay_type": 0,
      "tv_due_date": 0
    },
    "wallet": {
      "mid": 554384020,
      "bcoin_balance": 0,
      "coupon_balance": 0,
      "coupon_due_time": 0
    },
    "has_shop": false,
    "shop_url": "",
    "allowance_count": 0,
    "answer_status": 0,
    "is_senior_member": 0,
    "wbi_img": {
      "img_url": "https://i0.hdslb.com/bfs/wbi/7cd084941338484aae1ad9425b84077c.png",
      "sub_url": "https://i0.hdslb.com/bfs/wbi/4932caff0ff746eab6f01bf08b70ac45.png"
    },
    "is_jury": false
  }
}
```

### 返回结果

|状态码|状态码含义|说明|数据模型|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|成功|Inline|

### 返回数据结构

状态码 **200**

|名称|类型|必选|约束|中文名|说明|
|---|---|---|---|---|---|
|» code|integer|true|none||none|
|» message|string|true|none||none|
|» ttl|integer|true|none||none|
|» data|object|true|none||none|
|»» isLogin|boolean|true|none||none|
|»» wbi_img|object|true|none||none|
|»»» img_url|string|true|none||none|
|»»» sub_url|string|true|none||none|

# 搜索

## GET 默认搜索关键词

GET /x/web-interface/wbi/search/default

### 请求参数

|名称|位置|类型|必选|说明|
|---|---|---|---|---|
|User-Agent|header|string| 否 |none|

> 返回示例

> 200 Response

```json
{
  "code": 0,
  "message": "string",
  "ttl": 0,
  "data": {
    "seid": "string",
    "id": 0,
    "type": 0,
    "show_name": "string",
    "name": "string",
    "goto_type": 0,
    "goto_value": "string",
    "url": "string"
  }
}
```

### 返回结果

|状态码|状态码含义|说明|数据模型|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|成功|Inline|

### 返回数据结构

状态码 **200**

|名称|类型|必选|约束|中文名|说明|
|---|---|---|---|---|---|
|» code|integer|true|none||none|
|» message|string|true|none||none|
|» ttl|integer|true|none||none|
|» data|object|true|none||none|
|»» seid|string|true|none||none|
|»» id|integer|true|none||none|
|»» type|integer|true|none||none|
|»» show_name|string|true|none||none|
|»» name|string|true|none||none|
|»» goto_type|integer|true|none||none|
|»» goto_value|string|true|none||none|
|»» url|string|true|none||none|

# 消息

## GET 未读消息统计

GET /session_svr/v1/session_svr/single_unread

### 请求参数

|名称|位置|类型|必选|说明|
|---|---|---|---|---|
|buvid3=81E029EF-A437-932D-BDA6-1FE9A027797D18628infoc; i-wanna-go-back=-1; _uuid=43B16941-1FFC-10272-EBDE-7C5410F9857A519674infoc; FEED_LIVE_VERSION=V8; buvid4=AEC86992-33CA-0002-1E1B-6C4F8D4698D820049-023050212-cJA8FXQvRy4jVQ7t9q7YP3plA0h6wwfeu3CoOZGmiIHDmBsaVV1ZGQ%3D%3D; b_nut=1683002421; nostalgia_conf=-1; CURRENT_PID=65413a80-ea6a-11ed-bf6e-dd1745614af8; rpdid=|(u)YklYmm)Y0J'uY)Jum~)um; CURRENT_QUALITY=80; b_ut=5; CURRENT_BLACKGAP=0; buvid_fp_plain=undefined; header_theme_version=CLOSE; bp_video_offset_554384020=854175339141660677; bili_ticket=eyJhbGciOiJIUzI1NiIsImtpZCI6InMwMyIsInR5cCI6IkpXVCJ9.eyJleHAiOjE2OTc5ODI0MjIsImlhdCI6MTY5NzcyMzE2MiwicGx0IjotMX0.LPzZMT4jVf_9eYnLLeCgafMxM8KsrJHVaVBGiGKZoYY; bili_ticket_expires=1697982362; hit-dyn-v2=1; fingerprint=c5ae2885c5a3c440f09748e8308b60ca; buvid_fp=c5ae2885c5a3c440f09748e8308b60ca; enable_web_push=ENABLE; iflogin_when_web_push=0; b_lsid=396454F6_18B524DE196; bsource=search_baidu; LIVE_BUVID=AUTO4716978936118963; CURRENT_FNVAL=4048; home_feed_column=4; browser_resolution=814-707; PVID=1; SESSDATA=18cfaf91%2C1713448453%2C8b288%2Aa1CjBHfFD0WoHAA_6NayNvt6v4C9znBV0YJmsJT3Gn8qW7ZcGL5eXaXfsd1we9ZoAJQwYSVjhnSTdLaUxmak1iMnl4X243WXlQbDI0ZWwzWVRPX1RVZUNyTm45WVR2V2pXaEJaTzkwODNDVGRxMHJOcVUzcGxUVGt3bXp0MWlwLTVxejAyZ3ExTW5nIIEC; bili_jct=5e3d0d9afb7c63e8d771cb85fd897bd5; DedeUserID=554384020; DedeUserID__ckMd5=7260d1ed14bf3331; sid=mgat3hb|cookie|string| 否 |none|
|build|query|string| 否 |none|
|mobi_app|query|string| 否 |none|
|unread_type|query|string| 否 |none|
|User-Agent|header|string| 否 |none|

> 返回示例

> 200 Response

```json
{}
```

### 返回结果

|状态码|状态码含义|说明|数据模型|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|成功|Inline|

### 返回数据结构

# 收藏

## GET 收藏和订阅列表

GET /x/v3/fav/folder/collected/list

### 请求参数

|名称|位置|类型|必选|说明|
|---|---|---|---|---|
|pn|query|string| 否 |none|
|ps|query|string| 否 |none|
|up_mid|query|string| 否 |none|
|platform|query|string| 否 |none|
|User-Agent|header|string| 否 |none|

> 返回示例

> 200 Response

```json
{
  "code": 0,
  "message": "string",
  "ttl": 0,
  "data": null
}
```

### 返回结果

|状态码|状态码含义|说明|数据模型|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|成功|Inline|

### 返回数据结构

状态码 **200**

|名称|类型|必选|约束|中文名|说明|
|---|---|---|---|---|---|
|» code|integer|true|none||none|
|» message|string|true|none||none|
|» ttl|integer|true|none||none|
|» data|null|true|none||none|

## GET 收藏夹列表

GET /x/v3/fav/folder/created/list-all

### 请求参数

|名称|位置|类型|必选|说明|
|---|---|---|---|---|
|up_mid|query|string| 否 |none|
|User-Agent|header|string| 否 |none|

> 返回示例

> 200 Response

```json
{
  "code": 0,
  "message": "string",
  "ttl": 0,
  "data": null
}
```

### 返回结果

|状态码|状态码含义|说明|数据模型|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|成功|Inline|

### 返回数据结构

状态码 **200**

|名称|类型|必选|约束|中文名|说明|
|---|---|---|---|---|---|
|» code|integer|true|none||none|
|» message|string|true|none||none|
|» ttl|integer|true|none||none|
|» data|null|true|none||none|

## GET 收藏列表

GET /x/v3/fav/resource/list

### 请求参数

|名称|位置|类型|必选|说明|
|---|---|---|---|---|
|media_id|query|string| 否 |收藏夹id|
|pn|query|string| 否 |none|
|ps|query|string| 否 |none|
|keyword|query|string| 否 |搜索关键词|
|order|query|string| 否 |mtime最近收藏 view最多播放 pubtime最近投稿|
|type|query|string| 否 |0为当前收藏夹 1为全部收藏夹|
|tid|query|string| 否 |0为全部|
|platform|query|string| 否 |none|
|User-Agent|header|string| 否 |none|

> 返回示例

> 200 Response

```json
{}
```

### 返回结果

|状态码|状态码含义|说明|数据模型|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|成功|Inline|

### 返回数据结构

# 数据模型

