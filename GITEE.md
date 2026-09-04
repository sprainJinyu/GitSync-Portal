# Gitee 支持说明

这个仓库由 Grok 在 sprainJinyu 账号下新建（原仓库 fork 权限不足，无法直接 fork `kaleido1/GitSync-Portal`）。

## 现状

- 改动在 `gitee-support.patch`
- 还没有打好可直接装到手机的 `main.js`
- GitHub 功能保持不变；设置里可选 GitHub 或 Gitee

## 本机打包

```bash
git clone https://github.com/kaleido1/GitSync-Portal.git
cd GitSync-Portal
git apply gitee-support.patch
npm install
npm run build
```

把生成的 `main.js`、`manifest.json`、`styles.css` 覆盖到手机：

```text
你的库/.obsidian/plugins/gitsync-portal/
```

重启 Obsidian 后，设置里选 **Gitee**，填 Gitee 私人令牌和 `用户名/仓库名`，分支往往是 `master`。

## Gitee API

- 根地址：`https://gitee.com/api/v5`
- 鉴权：`access_token`
- 推送：`POST /repos/{owner}/{repo}/commits`（批量 actions）
- 拉取：`/branches/{branch}` + `/git/trees/{sha}` + `/git/blobs/{sha}`
