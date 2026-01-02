# ReactorNetCore

高性能网络库，基于 epoll 实现的 Reactor 模式，主要是为了实现KVS，此外支持 Echo 服务器、HTTP 服务和 WebSocket 服务。

## ✨ 核心特性

- 🚀 **高性能事件驱动架构**: 基于 epoll 的 Reactor 模式实现，支持水平触发(LT)和边沿触发(ET)模式
- 🌐 **多协议支持**: 原生支持 HTTP/1.1 和 WebSocket 协议
- 📊 **多级日志系统**: 支持 TRACE/DEBUG/INFO/WARN/ERROR 级别日志，带彩色输出和精确时间戳
- 🧩 **模块化设计**: 清晰分离网络层、协议层和应用层
- 🔍 **详细文档**: 包含架构设计和 API 说明
- 🧪 **完备测试工具**: Python 测试客户端支持压力测试和持续测试

## 📋 前置要求

- Linux 系统 (内核 ≥ 3.0)
- GCC ≥ 9.0
- Python ≥ 3.8 (仅测试需要)

## 🚀 快速开始

### 运行 Echo 服务器
```bash
./build/echo_server 8888
```

### 测试客户端连接
```bash
# 基础测试
python3 tests/echo_client.py 127.0.0.1 8888

# 压力测试 (100连接/秒)
python3 tests/echo_client.py 127.0.0.1 8888 --continuous 100

# 长连接测试 (维持60秒)
python3 tests/echo_client.py 127.0.0.1 8888 --duration 60
```

## 📁 项目结构
```
ReactorNetCore/
├── build/       # 编译输出
├── docs/        # 项目文档
│   ├── ARCHITECTURE.md  # 架构设计
│   ├── API_REFERENCE.md # API文档
│   └── LOGGING.md       # 日志系统指南
├── include/     # 头文件
│   ├── reactor/ # Reactor 模式实现
│   ├── logger/  # 日志系统
│   └── kv_store/ # KV存储
├── src/         # 源代码
├── tests/       # 测试工具
└── Makefile     # 构建脚本
```

## 🔨 构建选项
```bash
make          # 调试模式 (默认)
make release  # 发布模式 (-O2优化)
make clean    # 清理构建
make run      # 编译并运行echo_server
```

## 🚧 开发进度

| 模块 | 状态 | 进度 |
|------|------|------|
| Reactor 核心 | ✅ 完成 | 100% |
| 日志系统 | ✅ 完成 | 100% |
| Echo 服务器 | ✅ 完成 | 100% |
| KV 存储引擎 | ✅ 完成 | 100% |
| HTTP 协议支持 | ✅ 完成 | 100% |
| WebSocket 支持 | ✅ 完成 | 100% |

## 📄 许可证

本项目采用 [MIT 许可证](docs/LICENSE)

---
**项目状态**: 🔧 维护模式  
**最新更新**: 2025-12-31
