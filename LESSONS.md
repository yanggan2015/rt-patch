# 经验总结: 拉取最新 Linux RT Patch

## 遇到的问题 & 解决方案

1. **问题**: 补丁仅约 4.7KB，看似异常 → **解决**: 6.12 后 PREEMPT_RT 已主线化，out-of-tree 剩余改动很少，体积小属正常。
2. **问题**: wiki.linuxfoundation.org/realtime 被 Cloudflare 拦截 → **解决**: 以 kernel.org `projects/rt/` 目录与 sha256sums 为准。

## 关键发现

- “最新”优先看 `projects/rt/` 下最高主线大版本目录中的 `patch-*-rt*.patch.xz`。
- 若需要稳定/非 rc：当前可选用 `7.2-rt5`；LTS 常用 `6.12.x-rt*` / `6.6.x-rt*`。
- 打补丁必须匹配同版本主线标签（本补丁对应 `v7.3-rc4`）。

## 改进建议

- 可加脚本自动选最高版本目录并更新 `RT_PATCH_URL.md`。
- 生产环境优先选 LTS RT（如 6.12）而非最新 rc。
- 讲解 RT 时必须区分「主线 PREEMPT_RT 核心」与「projects/rt 残留 OOT」；只讲补丁 diff 会漏掉真实时能力。
