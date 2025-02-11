# SunshineAI-Codespace

SunshineAI-Codespace 是一个基于 Docker 和 GitHub Actions 的 AI 开发环境。本项目旨在提供一个标准化的开发环境，使团队成员能够快速开始 AI 相关的开发工作。通过容器化技术，我们确保了所有开发者都在相同的环境下工作，从而减少环境差异带来的问题。

## 技术栈

本项目使用了以下主要技术：

### 容器化技术
- **Docker**: 用于容器化应用程序和开发环境
  - 提供统一的开发环境
  - 确保开发和生产环境的一致性
  - 简化依赖管理

### CI/CD 工具
- **GitHub Actions**: 用于自动化构建和部署流程
  - 自动化镜像构建
  - 环境检测和验证
  - 多平台支持

### 跨平台支持
- **QEMU**: 用于跨平台容器模拟
  - 支持多架构编译
  - 实现跨平台运行
- **Docker Buildx**: 用于多平台 Docker 镜像构建
  - 支持 ARM64/AMD64 架构
  - 优化构建缓存
  - 并行构建能力

## 项目结构

```
.
├── .github/
│   └── workflows/
│       ├── Build-Devcontainer-Image.yml   # 开发容器镜像构建工作流
│       └── Detect-action-installed.yml     # 环境检测工作流
├── .devcontainer/                         # 开发容器配置
├── Dockerfile                             # Docker 镜像定义
├── LICENSE                                # MIT 许可证
└── README.md                              # 项目文档
```

## 自动化工作流

### 1. 开发容器镜像构建 (Build-Devcontainer-Image.yml)
- 自动构建开发环境 Docker 镜像
- 支持多平台构建（ARM64/AMD64）
- 自动推送到 GitHub Container Registry

### 2. 环境检测 (Detect-action-installed.yml)
- 检测运行环境中已安装的软件包
- 生成环境报告
- 上传检测结果作为构建产物

## 开发环境设置

### 前置要求
- Docker Desktop 安装并运行
- Git 客户端
- GitHub 账号
- VSCode（推荐）

### 本地开发步骤

1. 克隆仓库：
```bash
git clone https://github.com/your-username/SunshineAI-Codespace.git
cd SunshineAI-Codespace
```

2. 使用 VSCode 打开项目：
```bash
code .
```

3. 安装推荐的 VSCode 扩展：
   - Remote - Containers
   - Docker
   - GitHub Actions

4. 使用开发容器打开项目：
   - 点击 VSCode 左下角的绿色按钮
   - 选择 "Reopen in Container"

## 使用指南

### 开发容器
1. 开发容器已预装以下工具：
   - Python 开发环境
   - AI 框架和工具
   - 代码检查工具
   - Git 工具

2. 环境变量配置：
   - 在 `.devcontainer/devcontainer.json` 中配置
   - 支持自定义环境变量

### CI/CD 流程
1. 提交代码到主分支会自动触发：
   - 代码质量检查
   - 单元测试
   - 镜像构建

2. 手动触发工作流：
   - 在 GitHub Actions 页面触发
   - 支持自定义参数

## 常见问题解决

1. 容器构建失败
   - 检查 Docker 服务状态
   - 确认网络连接
   - 查看构建日志

2. 开发环境问题
   - 重建开发容器
   - 更新 Docker 镜像
   - 检查错误日志

## 贡献指南

1. Fork 本仓库
2. 创建特性分支 (`git checkout -b feature/AmazingFeature`)
3. 提交更改 (`git commit -m 'Add some AmazingFeature'`)
4. 推送到分支 (`git push origin feature/AmazingFeature`)
5. 开启一个 Pull Request

## 许可证

本项目采用 MIT 许可证 - 详见 [LICENSE](LICENSE) 文件

## 维护者

- 项目维护团队：SunshineAI Team
- 问题反馈：[Issues](https://github.com/your-username/SunshineAI-Codespace/issues)