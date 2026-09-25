# 手动执行步骤: 拉取最新 Linux RT Patch

## 前置条件

- 网络可访问 `cdn.kernel.org`
- 工具: `curl`, `xz`, `sha256sum`

## 步骤

### Step 1: 查看官方 RT 目录，确定最新大版本

```bash
curl -sL https://cdn.kernel.org/pub/linux/kernel/projects/rt/ | grep -oE 'href="[0-9][^"]+/"'
```

预期结果: 目录列表，当前最高为 `7.3/`（及更早版本）。

### Step 2: 列出该版本下补丁文件，取最新

```bash
VER=7.3
curl -sL "https://cdn.kernel.org/pub/linux/kernel/projects/rt/${VER}/" | grep -oE 'href="patch-[^"]+\.xz"'
```

预期结果: 出现 `patch-7.3-rc4-rt1.patch.xz`（名称随发布变化）。

### Step 3: 下载补丁、签名与校验和

```bash
mkdir -p patches
BASE=https://cdn.kernel.org/pub/linux/kernel/projects/rt/7.3
FILE=patch-7.3-rc4-rt1.patch.xz
curl -fL -o "patches/$FILE" "$BASE/$FILE"
curl -fL -o "patches/patch-7.3-rc4-rt1.patch.sign" "$BASE/patch-7.3-rc4-rt1.patch.sign"
curl -fL -o "patches/sha256sums.asc" "$BASE/sha256sums.asc"
```

预期结果: 三个文件落盘到 `patches/`。

### Step 4: 校验完整性

```bash
sha256sum -c <(grep "$(basename patches/$FILE)" patches/sha256sums.asc | sed "s|  |  patches/|")
xz -t "patches/$FILE"
```

预期结果: `OK` / `xz OK`。

### Step 5: 更新地址文档

将版本号、完整 URL、SHA256 写入 `RT_PATCH_URL.md` 与 `docs/RT_PATCH_SOURCE.md`。
