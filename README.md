# 文档测试

目录
[TOC]


## config
### function

#### getConfig
- 功能：拉取运营平台上的配置内容。关于运营平台的具体用法，参见{@link https://iwiki.woa.com/pages/viewpage.action?pageId&#x3D;527948584}
- category：配置相关
- scope：global

##### 回参(return):

| 字段名 | 类型 | 含义 |
| ----- | --- | --- |
| --- | Promise.<(Object|Array.<Object>)> | 有默认值时，请求失败返回默认值。无默认值时，请求失败返回Promise.reject |

##### 入参(params):

| 字段名 | 类型 | 含义 | 默认值 | 是否必传 |
| ----- | --- | --- | ----- | ----- |
| configPath | String|Array | 配置路径，单个路径或配置路径数组，支持替换${client}为当前小程序。例如在出行小程序，${client}会变替换为sinan |  | 否
| extendAttr | Object | 扩展属性，传给配置服务用于检索哪个版本的配置适用于当前用户。 |  | 否
| defaultCfg | Object | 默认配置，请求失败返回默认值。 |  | 是


##### 使用示例：
```javascript
<caption>拉取单个配置</caption>
const cfg = await app.tms.getConfig('/${client}/violation/subscribe', {}, { title: '当前城市不支持订阅'})
console.log(cfg); // 成功则返回服务端存储的配置，失败返回默认值
```
```javascript
<caption>批量拉取配置</caption>
const cfgs = await app.tms.getConfig([
  '/${client}/home/service',
  '/${client}/home/navbar',
], {}, [
  [
    { caption: '违章代缴', icon: 'violation.png' }
  ],
  { title: '晚上好，欢迎~' }
]);
console.log(cfgs); // 成功则返回服务端存储的配置，失败返回默认值
```

## location
### function

#### getLocation
- scope：global

##### 回参(return):

| 字段名 | 类型 | 含义 |
| ----- | --- | --- |
| --- | promise | 获取的定位结果 |

##### 入参(params):

| 字段名 | 类型 | 含义 | 默认值 | 是否必传 |
| ----- | --- | --- | ----- | ----- |
| type | string | 定位类型 |  | 否


#### openSetting
- scope：global

##### 回参(return):

| 字段名 | 类型 | 含义 |
| ----- | --- | --- |
| --- | promise | 授权页操作状态 |

##### 入参(params):

| 字段名 | 类型 | 含义 | 默认值 | 是否必传 |
| ----- | --- | --- | ----- | ----- |
| scopeKey | string | 授权项 |  | 否


## navigator
### function

#### navigateToWebview
- 功能：navigateToWebview 方法 跳转到小程序的 web-view 容器打开 H5
- scope：global

##### 回参(return):

| 字段名 | 类型 | 含义 |
| ----- | --- | --- |
| --- | undefined | 无返回值 |

##### 入参(params):

| 字段名 | 类型 | 含义 | 默认值 | 是否必传 |
| ----- | --- | --- | ----- | ----- |
| setting | object | 配置信息 |  | 否
| setting.url | string | 需要跳转的 H5 连接 |  | 否
| setting.complete | function | 跳转成功后的回调函数 |  | 否
| setting.message | function | 用于获取 H5 中的 postMessage 的数据 |  | 否
| setting.share | object | 页面分享信息 |  | 否
| setting.share.title | string | 页面分享标题 |  | 否
| setting.share.image | string | 页面分享图片 |  | 否
| setting.share.disable | string | 是否禁用页面分享 |  | 否
| setting.navbar | object | 页面导航栏设置 |  | 否
| setting.navbar.frontColor | string | 导航栏字体颜色 |  | 否
| setting.navbar.backgroundColor | string | 导航栏背景颜色 |  | 否


