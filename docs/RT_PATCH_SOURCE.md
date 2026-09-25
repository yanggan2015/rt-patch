# Linux RT Patch 官方地址

更新日期: 2026-09-26

## 当前拉取版本（最新）

| 项 | 值 |
|----|-----|
| 版本 | **7.3-rc4-rt1** |
| 基于内核 | linux-7.3-rc4 |
| 单文件补丁 | `patch-7.3-rc4-rt1.patch.xz` |
| SHA256 | `2ea957599d6202a34bd6b9500c5288dab12c3cf34d25fb4fcad0ca0dcff51412` |
| 本地路径 | `patches/patch-7.3-rc4-rt1.patch.xz` |

### 直接下载地址

```
https://cdn.kernel.org/pub/linux/kernel/projects/rt/7.3/patch-7.3-rc4-rt1.patch.xz
https://cdn.kernel.org/pub/linux/kernel/projects/rt/7.3/patch-7.3-rc4-rt1.patch.sign
https://cdn.kernel.org/pub/linux/kernel/projects/rt/7.3/patches-7.3-rc4-rt1.tar.xz
https://cdn.kernel.org/pub/linux/kernel/projects/rt/7.3/sha256sums.asc
```

镜像（同内容）:

```
https://www.kernel.org/pub/linux/kernel/projects/rt/7.3/patch-7.3-rc4-rt1.patch.xz
https://mirrors.edge.kernel.org/pub/linux/kernel/projects/rt/7.3/patch-7.3-rc4-rt1.patch.xz
```

## 官方目录索引

```
https://cdn.kernel.org/pub/linux/kernel/projects/rt/
```

按主线大版本分子目录（如 `7.3/`、`7.2/`、`6.12/`）。目录顶层最新大版本即为当前 RT 发布线。

## Git 树（可选）

| 用途 | 地址 |
|------|------|
| RT 开发树 | https://git.kernel.org/pub/scm/linux/kernel/git/rt/linux-rt-devel.git |
| RT stable | https://git.kernel.org/pub/scm/linux/kernel/git/rt/linux-stable-rt.git |
| 项目主页 | https://wiki.linuxfoundation.org/realtime/start |

## 同期参考版本（同日检索）

| 类型 | 版本 | 目录 |
|------|------|------|
| 最新（rc） | 7.3-rc4-rt1 | `.../rt/7.3/` |
| 最新正式（非 rc） | 7.2-rt5 | `.../rt/7.2/` |
| LTS 例 | 6.12.100-rt20 | `.../rt/6.12/` |
| 旧 LTS 例 | 6.6.156-rt79 | `.../rt/6.6/` |

## 说明

- 自 6.12 起 PREEMPT_RT 已大部分合入主线，后续 out-of-tree RT patch 体积极小（本版约 4.7KB）。
- 打补丁前需使用对应版本的主线源码（本补丁对应 `v7.3-rc4`）。
- 校验：对比 `sha256sums.asc` 中的哈希；签名文件为 `.sign`。
