# 关于 | About
此EFI专门用于主板B450M MORTAR(MAX)定制

无法保证其他主板的兼容性

This EFI is made for B450M MORTAR(MAX), can not guarantee compatibility with other motherboards and not fully functional.

关于 Opencore 0.7.2 更新使用注意事项
=
- 默认config为物理核心数为6的AMD CPU使用
- 如果你是 `4核` 或者 `8核` 以上的请使用对应的config，如 `4核` 使用config4c.plist, `8核` 使用config8c.plist

**>>>>>>如果你没有自行配置的需求，以下内容可跳过不看<<<<<<**

内核测试补丁更新至macOS 12 Monterey beta版本

对配置文件有配置要求，如下

| 核心数 | 数值|
|--------|---------|
|   4 Core  | `04` |
|   6 Core  | `06` |
|   8 Core  | `08` |
|   12 Core | `0C` |
|   16 Core | `10` |
|   24 Core | `18` |
|   32 Core | `20` |

用OpenCore Configurator打开config, 找到 Kernel -> Patch 前三项名为 `algrey - Force cpuid_cores_per_package` 的补丁，只需修改`Replace`的值

修改默认的 `B8000000 0000`/`BA000000 0000`/`BA000000 0090`* 为 `B8 <核心数> 0000 0000`/`BA <核心数> 0000 0000`/`BA <核心数> 0000 0090`* , 其中 `<核心数>` 代表的对应数值在上面的表格

举个例子 6核 的 5600X 需要修改替换的值即 `B8 06 0000 0000`/`BA 06 0000 0000`/`BA 06 0000 0090`

![](https://github.com/TheStupidNoob/B450M-MORTAR-OpencoreEFI/blob/main/test.png)
![](https://github.com/tekteq/opencanopy-minimal-theme/blob/main/Preview.png)
