# Amiya-CDN

> Amiya-CDN 是一个 CDN 服务，基于 Vercel + GcoreCDN 实现。

我们基于Python的FastAPI搭建回源中间件，使用Vercel进行部署，GcoreCDN进行CDN加速，初次回源速度较慢，待后续优化。

## GitHub

GitHub 回源自 `raw.githubusercontent.com`
```
/gh/[USER_NAME]/[REPO_NAME]@[BRANCH_NAME]/[FILE]
```

如果 `BRANCH_NAME` 未包含，则会默认为当前仓库的主分支。

## NPM

NPM 回源自 `unpkg.com`

```
/npm/[PACKAGE_NAME]@[VERSION]/[FILE]
```

需要注意的是，如果当前未指定版本号，或者版本号为`latest`，我们将会将请求重定向到当前包的最新版本

## Gravatar

Gravatar 回源自 `gravatar.com`

```
/avatar/[HASH]
```

## 刷新缓存

我们通过GcoreCDN的API进行缓存刷新

```
/purge/[URL]
```
请注意，`[URL]` 参数为需要刷新的路径

如

```
/purge/gh/Amiya-CDN/cdn-fontend@master/README.md
```
