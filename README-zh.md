# Kubernetes Release for LoongArch64

<p align="center">[English](README.md) | [中文](README-zh.md)</p>

<p align="center"><img src="https://img.shields.io/badge/Kubernetes%20LoongArch64%20Release-%E9%BE%99%E8%8A%AF%E6%9E%B6%E6%9E%84%E5%8F%91%E8%A1%8C%E7%89%88-blue" alt="Kubernetes LoongArch64 Release 龙芯架构发行版"></p>

本项目基于上游 [kubernetes/release](https://github.com/kubernetes/release) 工具链，通过 CI/CD 流水线构建 **LoongArch64 (loong64)**（龙芯）架构的 Kubernetes 发行版。

上游 Kubernetes 尚未正式支持龙芯架构，本项目填补了这一空白，为 **LoongArch64 (loong64)** 系统提供预构建的 **容器镜像**。

## 工作原理

1. **上游跟踪** — 本项目跟踪 [上游 kubernetes/release](https://github.com/kubernetes/release) 仓库，并引入与 **LoongArch64 (loong64)** 支持相关的变更。
2. **CI/CD 流水线** — 自动化流水线在 **LoongArch64 (loong64)** 硬件上原生构建或通过交叉编译生成 Kubernetes 组件。
3. **产物发布** — 构建好的容器镜像将发布供社区使用。

## 相关仓库

- [kubernetes/kubernetes](https://github.com/kubernetes/kubernetes) — 上游 Kubernetes 源码
- [kubernetes/release](https://github.com/kubernetes/release) — 上游发布工具
- [kubernetes/sig-release](https://github.com/kubernetes/sig-release) — Kubernetes SIG Release

## 贡献

欢迎贡献。请确保您的变更与上游发布流程保持一致，并且仅针对于 **LoongArch64 (loong64)** 架构的适配。

## 许可证

[Apache License 2.0](LICENSE)
