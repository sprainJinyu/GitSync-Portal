# GitSync Portal — GitHub + Gitee

另一个会话建了两个仓库：

- https://github.com/sprainJinyu/GitSync-Portal-fork  上游完整 fork（源码齐）
- https://github.com/sprainJinyu/GitSync-Portal  本仓库，GitHub App 能写入

双后端改动在 `gitee-support.patch`（若该文件仍是占位符，用会话里下发的完整 patch）。

## 打包

```bash
git clone https://github.com/sprainJinyu/GitSync-Portal-fork.git
cd GitSync-Portal-fork
git apply gitee-support.patch
npm install
npm run build
```

把 `main.js` `manifest.json` `styles.css` 拷到库的 `.obsidian/plugins/gitsync-portal/`。

设置里选 GitHub 或 Gitee，填令牌和 `owner/repo`。Token 输入框已改成明文，手机可直接粘贴。
