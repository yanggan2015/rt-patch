# 执行记录: 拉取最新 Linux RT Patch

日期: 2026-09-26

## 步骤

| # | 操作 | 文件/命令 | 结果 |
|---|------|-----------|------|
| 1 | 列出官方 RT 目录 | `curl https://cdn.kernel.org/pub/linux/kernel/projects/rt/` | ✅ 最新大版本 7.3 |
| 2 | 确认各版本最新补丁 | 扫描 7.3/7.2/7.1/7.0/6.19/... | ✅ 最新为 7.3-rc4-rt1 |
| 3 | 下载补丁与校验文件 | `curl` → `patches/` | ✅ |
| 4 | 校验 SHA256 / xz | `sha256sum` + `xz -t` | ✅ 哈希一致 |
| 5 | 记录官方地址 | `RT_PATCH_URL.md`, `docs/RT_PATCH_SOURCE.md` | ✅ |
| 6 | 下载 series 包并分析全部 hunk | `patches-7.3-rc4-rt1.tar.xz` | ✅ |
| 7 | 撰写功能/代码讲解文档 | `docs/RT_PATCH_EXPLAINED.md` | ✅ |
| 8 | 展开 series 到仓库 | `patches/series/` | ✅ |
| 9 | 撰写详细代码讲解（含目录） | `docs/RT_PATCH_DETAILED.md` | ✅ |
| 10 | 初始化 git 并推送 GitHub | `gh repo create` | ✅ |

## 修改文件清单

- `patches/patch-7.3-rc4-rt1.patch.xz`: 最新 RT 单文件补丁
- `patches/patches-7.3-rc4-rt1.tar.xz`: 系列拆分包
- `patches/series/`: 拆分补丁（含 `series` 清单）
- `patches/patch-7.3-rc4-rt1.patch.sign`: GPG 签名
- `patches/sha256sums.asc`: 官方校验和
- `RT_PATCH_URL.md`: 地址速查
- `docs/RT_PATCH_SOURCE.md`: 完整地址与参考版本
- `docs/RT_PATCH_EXPLAINED.md`: RT 功能精简讲解
- `docs/RT_PATCH_DETAILED.md`: 目录 + 逐文件代码详细讲解
- `README.md` / `STEPS.md` / `EXECUTION_LOG.md` / `LESSONS.md`

