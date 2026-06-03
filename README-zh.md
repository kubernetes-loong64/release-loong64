# Kubernetes Release for LoongArch64

<p align="center"><a href="README.md">English</a> | <a href="README-zh.md">中文</a></p>

<p align="center"><img src="https://img.shields.io/badge/Kubernetes%20Release%20LoongArch64%20%E9%BE%99%E8%8A%AF%E6%9E%B6%E6%9E%84%E5%8F%91%E8%A1%8C%E7%89%88-blue?logo=kubernetes&logoColor=white" alt="Kubernetes Release LoongArch64 龙芯架构发行版"></p>

本项目基于上游 [kubernetes/release](https://github.com/kubernetes/release) 工具链，通过 CI/CD 流水线构建 **LoongArch64 (loong64)**（龙芯）架构的 Kubernetes 发行版。

上游 Kubernetes 尚未正式支持龙芯架构，本项目填补了这一空白，为 **LoongArch64 (loong64)** 系统提供预构建的 **容器镜像**。

## 工作原理

1. **上游跟踪** — 本项目跟踪 [上游 kubernetes/release](https://github.com/kubernetes/release) 仓库，并引入与 **LoongArch64 (loong64)** 支持相关的变更。
2. **CI/CD 流水线** — 自动化流水线在 **LoongArch64 (loong64)** 硬件上原生构建或通过交叉编译生成 Kubernetes 组件。
3. **产物发布** — 构建好的容器镜像将发布供社区使用。

关于 Debian 13 容器选型的理由，详见 [Discussion #6 — 为什么使用 container: debian:13？](https://github.com/orgs/kubernetes-loong64/discussions/6)。

## 分支与标签命名

- 推送 `loong64-<版本>` 格式的分支（如 `loong64-v0.21.1-3`）可触发 CI 构建，构建产物仅发布至本地 CI 镜像仓库。
- 推送 `release-loong64-<版本>` 格式的标签（如 `release-loong64-v0.21.1+3`）可触发正式发布，将多架构镜像发布至 Docker Hub 并创建附有签名产物的 GitHub Release。

## 容器镜像

这些镜像由 [kubernetes/release](https://github.com/kubernetes/release) 为 **LoongArch64 (loong64)** 构建。

1. 镜像标签带 `-<数字>` 后缀（如 `v0.21.1-1`、`v0.21.1-2`）的是 CI/CD 构建序号，依次递增，整个项目唯一，仅作为历史版本保留。
2. 使用不带 `-<数字>` 的 `vX.Y.Z` 版本号即可获取该版本的最新构建。

- [![kubernetesloong64/debian-base](https://img.shields.io/docker/v/kubernetesloong64/debian-base?logo=docker&label=kubernetesloong64%2Fdebian-base)](https://hub.docker.com/r/kubernetesloong64/debian-base/tags)
- [![kubernetesloong64/distroless-iptables](https://img.shields.io/docker/v/kubernetesloong64/distroless-iptables?logo=docker&label=kubernetesloong64%2Fdistroless-iptables)](https://hub.docker.com/r/kubernetesloong64/distroless-iptables/tags)
- [![kubernetesloong64/go-runner](https://img.shields.io/docker/v/kubernetesloong64/go-runner?logo=docker&label=kubernetesloong64%2Fgo-runner)](https://hub.docker.com/r/kubernetesloong64/go-runner/tags)
- [![kubernetesloong64/setcap](https://img.shields.io/docker/v/kubernetesloong64/setcap?logo=docker&label=kubernetesloong64%2Fsetcap)](https://hub.docker.com/r/kubernetesloong64/setcap/tags)

## 相关仓库

- [kubernetes/kubernetes](https://github.com/kubernetes/kubernetes) — 上游 Kubernetes 源码
- [kubernetes/release](https://github.com/kubernetes/release) — 上游发布工具
- [kubernetes/sig-release](https://github.com/kubernetes/sig-release) — Kubernetes SIG Release

## 贡献

欢迎贡献。请确保您的变更与上游发布流程保持一致，并且仅针对于 **LoongArch64 (loong64)** 架构的适配。

## 许可证

[Apache License 2.0](LICENSE)
