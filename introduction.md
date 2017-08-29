# 简介

2个目的：
* 实现一个完整的Linux文件系统
* 尝试各种文件系统实现方案

# Linux文件系统

Linux VFS定义了一个完整的文件系统所需要提供的接口，从功能来划分有8类：

* 挂载相关
`file_system_type`
`super_operations`

* 目录项相关
`dentry_operations`

* 文件元信息相关
`inode_operations`
`iomap_ops`

* 文件读写相关
`file_operations`

* 页缓存相关
`address_space_operation`
`vm_operations_struct`

* 扩展属性相关
`xattr_handler`

* 配额控制相关
`quotactl_ops`

* NFS相关
`export_operations`

本系列将详细介绍这些接口的含义和使用。

# 文件系统实现方案

从保证文件系统一致性的原理来说，有4类：
* Logging (write-ahead) Filesystem
* Log-Structured Filesystem
* COW Filesystem
* Soft Update Filesystem

本系统将分别实现这4种文件系统。

