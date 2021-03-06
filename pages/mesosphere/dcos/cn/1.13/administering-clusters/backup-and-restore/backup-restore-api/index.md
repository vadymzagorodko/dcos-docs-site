---
layout: layout.pug
navigationTitle:  备份和恢复 API
title: 备份和恢复 API
menuWeight: 10
excerpt: 使用 API 备份和恢复群集
enterprise: true
render: mustache
model: /mesosphere/dcos/1.13/data.yml
---

您可以使用“备份和恢复 API”来创建和恢复群集的备份。

<p class="message--important"><strong>重要信息：</strong>查看<a href="/mesosphere/dcos/cn/1.13/administering-clusters/backup-and-restore/#limitations">限制</a>部分。</p>


# 路由

对备份和恢复 API 的访问是通过每个管理节点上的 Admin Router 使用以下路由以代理的方式完成：

```
/system/v1/backup/v1
```

要确定群集的 URL，请参阅 [群集访问](/mesosphere/dcos/cn/1.13/api/access/)。

# 格式

备份和恢复 API 请求和响应主体在 JSON 中格式化。请求必须包含 `accept` 标题：

```
Accept: application/json
```

回答包含 `content type` 标题：

```
Content-Type: application/json
```

# 身份认证

使用所有备份和恢复 API 路由都需要身份验证。

要验证 API 请求，请参阅 [获取认证令牌](/mesosphere/dcos/cn/1.13/security/ent/iam-api/#obtaining-an-authentication-token) 和 [传递认证令牌](/mesosphere/dcos/cn/1.13/security/ent/iam-api/#passing-an-authentication-token)。

备份和恢复 API 还需要通过以下权限授权：

| 资源 ID | 操作 |
|-------------|--------|
| `dcos:adminrouter:ops:system-backup` | `full` |

所有路由也可以被具有 `dcos:superuser` 权限的用户抵达。

要为您的帐户分配权限，请参阅 [权限参考](/mesosphere/dcos/cn/1.13/security/ent/perms-reference/)。


# API 参考

备份和恢复 API 允许您管理 DC/OS 群集上的备份和恢复操作。

[swagger api='/mesosphere/dcos/1.13/api/backup-restore.yaml']
