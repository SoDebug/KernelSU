# 常见问题

## KernelSU 是否支持我的设备 ？

首先，您的设备应该能够解锁 bootloader。 如果不能，则不支持。

然后在你的设备上安装 KernelSU 管理器并打开它，如果它显示 `不支持` ，那么你的设备是不受支持的；但你可以自己编译内核来使用。

## KernelSU 是否需要解锁 Bootloader ？

当然需要。

## KernelSU 是否支持模块 ？

支持，但它是早期版本，可能有问题。请等待它稳定 :)

## KernelSU 是否支持 Xposed ？

支持，[Dreamland](https://github.com/canyie/Dreamland) 和 [TaiChi](https::/taichi.cool) 现在部分可用，我们正在努力使其他 Xposed Framework 可用。

## KernelSU 与 Magisk 兼容吗 ？

KernelSU 的模块系统与 Magisk 的 magic mount 有冲突，如果 KernelSU 中启用了任何模块，那么整个 Magisk 将无法工作。

但是如果你只使用 KernelSU 的 `su`，那么它会和 Magisk 一起工作：KernelSU 修改 `kernel` 、 Magisk 修改 `ramdisk`，它们可以一起工作。

## KernelSU 会替代 Magisk 吗？

我们不这么认为，这也不是我们的目标。Magisk 对于用户空间 root 解决方案来说已经足够好了，它会存活很久。KernelSU 的目标是为用户提供内核接口，而不是替代 Magisk。

## KernelSU 可以支持非 GKI 设备吗？

可以。但是你应该下载内核源代码并将 KernelSU 集成到源代码树中并自己编译内核。

## KernelSU 支持 Android 12 以下的设备吗？

影响 KernelSU 兼容性的是设备内核的版本，它与设备的 Android 版本没有直接的关系。唯一有关联的是：**出厂** Android 12 的设备，一定是 5.10 或更高的内核（GKI设备）；因此结论如下：

1. 出厂 Android 12 的设备必定是支持的（GKI 设备）
2. 旧版本内核的设备（即使是 Android 12，也可能是旧内核）是兼容的（你需要自己编译内核）

## KernelSU 可以支持旧内核吗？

可以，目前最低支持到 4.14；更低的版本你需要手动移植它，欢迎 PR ！

## 如何为旧内核集成 KernelSU？

参考[教程](how-to-integrate-for-non-gki)