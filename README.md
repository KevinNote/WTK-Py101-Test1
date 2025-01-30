# 梧桐 Py101 测验 1

> 适用于梧桐 Py101 课程

## 测验要求

测验按照如下要求进行：
- 测验所接受的语言 Python 或 Go, 你可以选择任意库（包括但是不局限于 django 和 flask）。但是请正确填写 `requirements.txt` （或 `go.mod` 对于使用 Go），因为这会用于环境初始化。
- 请独立完成。不要使用人工智能（包括但不局限于 ChatGPT、Claude、DeepSeek 与 Kimi等），这会导致测试结果不准确。
- 完成代码内容后可以请求你的督导者进行代码提交。

## 测验内容

你被要求完成一个简易的 Web 服务器，其是一个类似 QQ 签名的系统。

### LO1: Web 服务器的基本设置 (70%)

每个用户拥有一个简短的用户签名（bio），用户被定义为一个拥有用户名（`username`），密码（`password`）和个性签名（`bio`）的实体。

用户可以注册 `/register`，更改自己的个性签名 `/upd`。而对于大众，可以通过 `/user` 获取用户的个性签名。

- 正确填写 `requirements.txt`: 10%
- 完成注册 `/register`：20%
- 完成更新 `/register`：20%
- 完成获取签名 `/user`：20%

### LO2: 持久化 (30%)

服务器可以重启，而数据可能会丢失！这很不好。我们可以设置一个 `users.json` 的文件，其包含了现有所有用户的信息。在每次更新或者注册时，可以写入这个文件。

当服务器重启后可以读取这个 `user.json` 文件来恢复之前的用户数据。

## API 定义

```
POST /user
请求类型 JSON
请求格式:
{
  "username": <string>,
}

响应类型 JSON
响应格式：
{
  "bio": <string>
}
```

```
POST /register
请求格式:
{
  "username": <string>,
  "password": <string>
}

响应类型 JSON
响应格式：
{
  "ok": <bool>
}
```

```
POST /update
请求格式:
{
  "username": <string>,
  "password": <string>,
  "bio": <string>
}

响应类型 JSON
响应格式：
{
  "ok": <bool>
}
```
