# 文档测试

目录
[TOC]


## config
### function

#### getConfig
##### 功能：
拉取运营平台上的配置内容。关于运营平台的具体用法，参见{@link https://iwiki.woa.com/pages/viewpage.action?pageId&#x3D;527948584}
##### category：
配置相关
##### scope：
global
##### 回参(return)：

| 字段名 | 类型 | 含义 |
| ----- | --- | --- |
|  | [object Object] | 有默认值时，请求失败返回默认值。无默认值时，请求失败返回Promise.reject |
##### 入参(params):

| 字段名 | 类型 | 含义 | 默认值 | 是否必传 |
| ----- | --- | --- | ----- | ----- |
| configPath | [object Object] | 配置路径，单个路径或配置路径数组，支持替换${client}为当前小程序。例如在出行小程序，${client}会变替换为sinan |  | 
| extendAttr | [object Object] | 扩展属性，传给配置服务用于检索哪个版本的配置适用于当前用户。 |  | 
| defaultCfg | [object Object] | 默认配置，请求失败返回默认值。 |  | true

##### 使用示例：



## location
### function

#### getLocation
##### scope：
global
##### 回参(return)：

| 字段名 | 类型 | 含义 |
| ----- | --- | --- |
|  | [object Object] | 获取的定位结果 |
##### 入参(params):

| 字段名 | 类型 | 含义 | 默认值 | 是否必传 |
| ----- | --- | --- | ----- | ----- |
| type | [object Object] | 定位类型 |  | 

#### openSetting
##### scope：
global
##### 回参(return)：

| 字段名 | 类型 | 含义 |
| ----- | --- | --- |
|  | [object Object] | 授权页操作状态 |
##### 入参(params):

| 字段名 | 类型 | 含义 | 默认值 | 是否必传 |
| ----- | --- | --- | ----- | ----- |
| scopeKey | [object Object] | 授权项 |  | 

## navigator
### function

#### navigateToWebview
##### 功能：
navigateToWebview 方法 跳转到小程序的 web-view 容器打开 H5
##### scope：
global
##### 回参(return)：

| 字段名 | 类型 | 含义 |
| ----- | --- | --- |
|  | [object Object] | 无返回值 |
##### 入参(params):

| 字段名 | 类型 | 含义 | 默认值 | 是否必传 |
| ----- | --- | --- | ----- | ----- |
| setting | [object Object] | 配置信息 |  | 
| setting.url | [object Object] | 需要跳转的 H5 连接 |  | 
| setting.complete | [object Object] | 跳转成功后的回调函数 |  | 
| setting.message | [object Object] | 用于获取 H5 中的 postMessage 的数据 |  | 
| setting.share | [object Object] | 页面分享信息 |  | 
| setting.share.title | [object Object] | 页面分享标题 |  | 
| setting.share.image | [object Object] | 页面分享图片 |  | 
| setting.share.disable | [object Object] | 是否禁用页面分享 |  | 
| setting.navbar | [object Object] | 页面导航栏设置 |  | 
| setting.navbar.frontColor | [object Object] | 导航栏字体颜色 |  | 
| setting.navbar.backgroundColor | [object Object] | 导航栏背景颜色 |  | 

