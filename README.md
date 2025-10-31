# GoECS Android App

GoECS 服务器性能测试工具的 Android 版本。支持 **图形界面模式** 和 **命令行模式**。

## ✨ 特性

- ✅ **双模式运行**: 图形界面 (GUI) / 命令行 (CLI)
- ✅ **7 种测试项目**
  - 基础信息测试 (系统信息、IP 信息)
  - CPU 性能测试 (sysbench/geekbench/winsat)
  - 内存性能测试
  - 磁盘性能测试 (fio/dd)
  - 网络测速
  - 流媒体解锁测试
  - 路由追踪测试
- ✅ **后台执行 + 实时进度**
- ✅ **结果导出**
- ✅ **完整的参数支持**

## 🚀 快速开始

### GUI 模式（图形界面）

```bash
# 直接运行（默认启动 GUI）
./goecs-android

# 或明确指定 GUI 模式
./goecs-android -gui
```

### CLI 模式（命令行）

```bash
# 运行所有测试
./goecs-android -all

# 运行指定测试
./goecs-android -basic -cpu -memory

# 指定配置运行
./goecs-android -cpu -cpu-method sysbench -thread multi
./goecs-android -disk -disk-path /tmp -disk-method fio

# 英文环境
./goecs-android -all -lang en
```

## 📖 命令行参数

### 模式选择
- `-gui`: 启动图形界面模式（默认）

### 测试项
- `-basic`: 基础信息测试
- `-cpu`: CPU 性能测试
- `-memory`: 内存性能测试
- `-disk`: 磁盘性能测试
- `-speed`: 网络测速
- `-unlock`: 流媒体解锁测试
- `-route`: 路由追踪测试
- `-all`: 运行所有测试

### 配置选项
- `-lang string`: 语言 (zh/en，默认: zh)
- `-cpu-method string`: CPU 测试方法 (sysbench/geekbench/winsat，默认: sysbench)
- `-thread string`: 线程模式 (single/multi，默认: multi)
- `-disk-path string`: 磁盘测试路径（默认: 自动检测）
- `-disk-method string`: 磁盘测试方法 (fio/dd/auto，默认: auto)

### 其他
- `-version, -v`: 显示版本信息
- `-help, -h`: 显示帮助信息

## 🔨 本地开发

### 桌面调试（快速测试 UI）
```bash
go run .
```

### 编译二进制
```bash
go build -o goecs-android .
```

### 构建 Android APK
```bash
fyne package -os android -appID com.oneclickvirt.goecs -name GoECS
```

## 🤖 自动构建

推送到 `android-app` 分支会自动触发 CI 构建 APK。

## 📦 技术栈

- **UI 框架**: Fyne v2.4.5
- **语言**: Go 1.24.5
- **核心依赖**: github.com/oneclickvirt/ecs v0.1.91
- **最低 Android 版本**: Android 7.0 (API Level 24+)

## 🌳 分支说明

这是一个**孤儿分支**（orphan branch），与 master 分支完全独立：
- ✅ 没有 master 的提交历史
- ✅ 根目录直接是应用代码
- ✅ 使用远程依赖而非本地引用
- ✅ 独立的 CI/CD 流程

## 📝 许可证

遵循 https://github.com/oneclickvirt/ecs 项目的许可证。
