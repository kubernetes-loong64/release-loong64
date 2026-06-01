# Kubernetes Release for LoongArch64

<p align="center"><a href="README.md">English</a> | <a href="README-zh.md">中文</a></p>

<p align="center"><img src="https://img.shields.io/badge/Kubernetes%20Release%20LoongArch64%20%E9%BE%99%E8%8A%AF%E6%9E%B6%E6%9E%84%E5%8F%91%E8%A1%8C%E7%89%88-blue?logo=kubernetes&logoColor=white" alt="Kubernetes Release LoongArch64 龙芯架构发行版"></p>

This project builds Kubernetes releases for the **LoongArch64 (loong64)** (龙芯) architecture using CI/CD pipelines based on the upstream [kubernetes/release](https://github.com/kubernetes/release) tooling.

The LoongArch architecture is not yet officially supported by upstream Kubernetes. This project fills that gap by providing pre-built **container images** for **LoongArch64 (loong64)** systems.

## How It Works

1. **Upstream tracking** — This project tracks the [upstream kubernetes/release](https://github.com/kubernetes/release) repository and pulls in changes relevant to **LoongArch64 (loong64)** support.
2. **CI/CD pipeline** — Automated pipelines build Kubernetes components natively on **LoongArch64 (loong64)** hardware or via cross-compilation.
3. **Artifacts** — Built container images are published for community use.

See [Discussion #6 — Why Use container: debian:13?](https://github.com/orgs/kubernetes-loong64/discussions/6) for the rationale behind the Debian 13 container choice.

## Branch naming

Push a branch named `loong64/<release-version>` (e.g. `loong64/v0.21.1`) to trigger a build.

## Container Images

These images are built from [kubernetes/release](https://github.com/kubernetes/release) for **LoongArch64 (loong64)**.

1. Image tags with a `-<number>` suffix (e.g. `v0.21.1-1`, `v0.21.1-2`) are CI/CD build sequence numbers, unique across the project, kept as historical versions.
2. Use the plain `vX.Y.Z` tag (without the `-<number>` suffix) to get the latest build of that version.

- [![kubernetesloong64/debian-base](https://img.shields.io/docker/v/kubernetesloong64/debian-base?logo=docker&label=kubernetesloong64%2Fdebian-base)](https://hub.docker.com/r/kubernetesloong64/debian-base/tags)
- [![kubernetesloong64/distroless-iptables](https://img.shields.io/docker/v/kubernetesloong64/distroless-iptables?logo=docker&label=kubernetesloong64%2Fdistroless-iptables)](https://hub.docker.com/r/kubernetesloong64/distroless-iptables/tags)
- [![kubernetesloong64/go-runner](https://img.shields.io/docker/v/kubernetesloong64/go-runner?logo=docker&label=kubernetesloong64%2Fgo-runner)](https://hub.docker.com/r/kubernetesloong64/go-runner/tags)
- [![kubernetesloong64/setcap](https://img.shields.io/docker/v/kubernetesloong64/setcap?logo=docker&label=kubernetesloong64%2Fsetcap)](https://hub.docker.com/r/kubernetesloong64/setcap/tags)

## Related Repositories

- [kubernetes/kubernetes](https://github.com/kubernetes/kubernetes) — Upstream Kubernetes source
- [kubernetes/release](https://github.com/kubernetes/release) — Upstream release tooling
- [kubernetes/sig-release](https://github.com/kubernetes/sig-release) — Kubernetes SIG Release

## Contributing

Contributions are welcome. Please ensure your changes align with the upstream release process and are specific to **LoongArch64 (loong64)** enablement.

## License

[Apache License 2.0](LICENSE)
