# TMS FRAMEWORK DOC

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
| --- | <code>Promise.<(Object\|Array.<Object>)></code> | 有默认值时，请求失败返回默认值。无默认值时，请求失败返回Promise.reject |

##### 入参(params):

| 字段名 | 类型 | 含义 | 默认值 | 是否必传 |
| ----- | --- | --- | ----- | ----- |
| configPath | <code>String</code>\|<code>Array</code> | 配置路径，单个路径或配置路径数组，支持替换${client}为当前小程序。例如在出行小程序，${client}会变替换为sinan | --- | 否
| extendAttr | <code>Object</code> | 扩展属性，传给配置服务用于检索哪个版本的配置适用于当前用户。 | --- | 否
| defaultCfg | <code>Object</code> | 默认配置，请求失败返回默认值。 | --- | 是


##### 使用示例：

**Example** *(拉取单个配置)*
```js
const cfg = await app.tms.getConfig('/${client}/violation/subscribe', {}, { title: '当前城市不支持订阅'})
console.log(cfg); // 成功则返回服务端存储的配置，失败返回默认值
```
    

**Example** *(批量拉取配置)*
```js
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
| --- | <code>promise</code> | 获取的定位结果 |

##### 入参(params):

| 字段名 | 类型 | 含义 | 默认值 | 是否必传 |
| ----- | --- | --- | ----- | ----- |
| type | <code>string</code> | 定位类型 | --- | 否


#### openSetting
- scope：global

##### 回参(return):

| 字段名 | 类型 | 含义 |
| ----- | --- | --- |
| --- | <code>promise</code> | 授权页操作状态 |

##### 入参(params):

| 字段名 | 类型 | 含义 | 默认值 | 是否必传 |
| ----- | --- | --- | ----- | ----- |
| scopeKey | <code>string</code> | 授权项 | --- | 否


## navigator
### function

#### navigateToWebview
- 功能：navigateToWebview 方法 跳转到小程序的 web-view 容器打开 H5
- scope：global

##### 回参(return):

| 字段名 | 类型 | 含义 |
| ----- | --- | --- |
| --- | <code>undefined</code> | 无返回值 |

##### 入参(params):

| 字段名 | 类型 | 含义 | 默认值 | 是否必传 |
| ----- | --- | --- | ----- | ----- |
| setting | <code>object</code> | 配置信息 | --- | 否
| setting.url | <code>string</code> | 需要跳转的 H5 连接 | --- | 否
| setting.complete | <code>function</code> | 跳转成功后的回调函数 | --- | 否
| setting.message | <code>function</code> | 用于获取 H5 中的 postMessage 的数据 | --- | 否
| setting.share | <code>object</code> | 页面分享信息 | --- | 否
| setting.share.title | <code>string</code> | 页面分享标题 | --- | 否
| setting.share.image | <code>string</code> | 页面分享图片 | --- | 否
| setting.share.disable | <code>string</code> | 是否禁用页面分享 | --- | 否
| setting.navbar | <code>object</code> | 页面导航栏设置 | --- | 否
| setting.navbar.frontColor | <code>string</code> | 导航栏字体颜色 | --- | 否
| setting.navbar.backgroundColor | <code>string</code> | 导航栏背景颜色 | --- | 否


