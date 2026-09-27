# Linux RT Patch 笔记

官方 PREEMPT_RT 补丁笔记（当前：**7.3-rc4-rt1**）。

## 文档（按顺序）

| 文档 | 用途 |
|------|------|
| [docs/RT简明.md](docs/RT简明.md) | 非 RT → RT → 补丁（零基础原理） |
| [docs/RT详解.md](docs/RT详解.md) | 目录 + series 源码对照 |
| [docs/RT历史里程碑.md](docs/RT历史里程碑.md) | 官方历史重大主题 |
| [docs/RT隔离核与共享资源干扰.md](docs/RT隔离核与共享资源干扰.md) | 隔离核仍抖：共享缓存/内存/IO 与护航栈 |
| [docs/RT护航算法-快速切断非隔离核资源.md](docs/RT护航算法-快速切断非隔离核资源.md) | **软件快切：护航状态机 + cgroup/resctrl 执行器** |

地址：[`RT_PATCH_URL.md`](RT_PATCH_URL.md)。材料：`patches/`、`patches/series/`。


