# 哔咔漫画 · 增强版（Breeze 插件）

这是与 Breeze 官方插件并存的增强版本，使用独立插件 ID 和独立更新渠道，不覆盖官方哔咔插件。插件保留内容请求、登录、搜索、排行等能力；分类页沿用带预览图的网格，热搜数据由宿主搜索页展示。配套 Breeze 客户端根据插件清单中的 `breezeExperience` 呈现“我的”、完整分类屏蔽栏与默认详细列表；封面网格可手动切换。

## 安装与更新

在配套 Breeze 客户端的插件商城中找到「哔咔漫画 · 增强版」，点击「下载」；后续版本点击「下载更新」。发布包托管于本仓库的 GitHub Releases，商城目录位于 [`catalog/plugins_data.json`](catalog/plugins_data.json)。官方插件及目录不受影响。

旧版哔咔插件的账号会话不会自动迁移，需要在增强版中重新登录；旧版的本地收藏、历史和下载会在增强版「我的」中显示。

## 发布新版本

1. 更新 `src/info.ts` 中的版本号与功能，保持插件 UUID 不变。
2. 运行 `pnpm build`、`pnpm lint` 和 `pnpm format:check`；检查生成的 `manifest.json`。
3. 为相同版本创建 GitHub Release，上传 `dist/breeze-plugin-bika-comic.bundle.cjs.br`、`dist/breeze-plugin-bika-comic.bundle.cjs` 和 `manifest.json`。
4. 将 `catalog/plugins_data.json` 的版本号及 `updateUrl` 中的 Release 标签同时更新为发布版本并推送。商城刷新后会提示更新。

发布顺序应先有可下载的 Release，再让目录指向新版本，避免商城显示更新却无法安装。
