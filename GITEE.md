# GitHub + Gitee

- GitHub：Git Data API（blobs/trees/commits/refs）
- Gitee：`https://gitee.com/api/v5`，读 branches/commits/trees/blobs，写 `POST /repos/{owner}/{repo}/commits` + actions
- 设置项 `syncHost`: `github` | `gitee`
- Token 仍走 SecretStorage，每设备单独填
