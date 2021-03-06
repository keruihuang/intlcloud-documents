## 1. 接口描述
本接口 (CertDelete) 用于删除证书。
接口请求域名：<font style="color:red">wss.api.qcloud.com</font>

## 2. 输入参数
以下请求参数列表仅列出了接口请求参数，正式调用时需要加上公共请求参数，见 [公共请求参数](https://intl.cloud.tencent.com/document/api/377/4153) 页面。其中，此接口的 Action 字段为 CertDelete。

| 参数名称 | 是否必选  | 类型 | 描述 |
|---------|---------|---------|---------|
| ID | 是 | String | 证书 ID，即通过 GetList 拿到的证书列表的 ID 字段 |

## 3. 输出参数
| 参数名称 | 类型 | 描述 |
|---------|---------|---------|
| code | Int | 公共错误码, 0 表示成功，其他值表示失败。 |
| message | String | 模块错误信息描述，与接口相关。|
| codeDesc | String | 英文错误码，成功返回 Success，失败有相应的英文说明。|

>**注意**：   

>1. 免费 SSL 证只有在“验证失败”的状态下才能进行删除；
>2. 付费 SSL 证书只有在“终止审核”或“审核失败”状态下才能进行删除；
>3. 关联了负载均衡的 SSL 证书，不能删除；
>4. 上传托管的 SSL 证书除上述第 3 点情况外，其他情况下均可删除。
>

## 4. 示例
```
https://wss.test.api.qcloud.com/v2/index.php?
&<公共请求参数>
&Action=CertDelete
&id=xxxxxxxx

```
返回示例如下：

```
{
    "code": 0,
    "message": "",
    "codeDesc": "Success",
    "data": []
}

```
