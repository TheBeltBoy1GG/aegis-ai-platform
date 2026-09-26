# aegis-ai-platform

面向 AI 应用的一体化平台，提供模型接入、推理调度与应用管理能力。

## 技术栈

- Python 3.12
- uv（Python 包与环境管理工具）
- FastAPI / Uvicorn（API 服务，规划中）

## 目录结构
text
aegis-ai-platform/
├── apps/ # 业务应用（如 apps/api）
├── packages/ # 共享库
├── docs/ # 项目文档
└── infra/ # 基础设施与部署配置
## 如何运行

### 前置要求

- 已安装 [uv](https://docs.astral.sh/uv/)
- Python 3.12（uv 可自动下载）

### 启动 API 服务
bash
cd apps/api
uv sync
uv run python main.py
如果后续将 `main.py` 改造为 FastAPI 应用，则运行：
bash
cd apps/api
uv sync
uv run uvicorn main:app --reload
然后访问：

- 本地服务：http://localhost:8000

## 常用命令
bash
在 apps/api 下添加依赖
uv add fastapi uvicorn
添加开发依赖
uv add --dev pytest ruff
按锁文件同步环境（CI 推荐）
uv sync --frozen
运行测试
uv run pytest
## 环境变量

复制 `.env.example` 为 `.env` 并按需修改：
bash
cp .env.example .env