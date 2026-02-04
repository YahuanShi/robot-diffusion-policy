# Environment Backup – robodiff_u22

本目录用于备份与复现 **Conda 环境 `robodiff_u22`**，记录当前环境中已安装的 Conda / pip 依赖、渠道信息以及可复现配置文件

> ⚠️ 本目录仅包含 Conda / pip 层依赖，不包含系统级依赖（如 CUDA 驱动、librealsense、udev 规则等）。

---

## 目录结构

env_backup/
├── conda_channels.robodiff_u22.txt
├── conda_explicit_robodiff_u22.txt
├── conda_list.robodiff_u22.txt
├── requirements_robodiff_u22.txt
├── robodiff_u22_nobuilds.yaml
└── robodiff_u22.yaml


---

## 文件说明

### `robodiff_u22.yaml`
- 由 `conda env export` 生成
- 包含 Conda + pip 的完整环境信息
- 适用于相同或高度相似的平台
- 可能包含 build hash，跨平台稳定性较差

---

### `robodiff_u22_nobuilds.yaml`
- 由 `conda env export --no-builds` 生成
- 不包含 build string
- **推荐作为长期保存和跨机器复现使用**

---

### `conda_explicit_robodiff_u22.txt`
- 由 `conda list --explicit` 生成
- 精确锁定 Conda 包版本和来源
- 仅适用于相同操作系统与架构

---

### `conda_list.robodiff_u22.txt`
- 由 `conda list` 生成
- 人类可读性最好
- 适合用于对比环境变化（diff）

---

### `requirements_robodiff_u22.txt`
- 由 `pip freeze` 生成
- 仅包含通过 pip 安装的 Python 包
- 不包含 Conda 安装的包

---

### `conda_channels.robodiff_u22.txt`
- 记录 Conda channels 及其优先级
- 对环境解析与复现顺序很重要

---

## 环境复现方式

### 推荐方式（通用）
```bash
conda env create -f robodiff_u22_nobuilds.yaml


## 精确方式（同平台）
conda create -n robodiff_u22 --file conda_explicit_robodiff_u22.txt