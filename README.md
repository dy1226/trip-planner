# 🌍 TripFlow Trip Planner

一个使用 AI 驱动的智能旅游规划助手。结合了 AI 代理框架、高德地图 API 和 LLM，为用户创建个性化的旅行计划。

## 功能特性

- 🤖 **AI 驱动规划**：使用大语言模型生成智能旅行建议
- 🗺️ **地图集成**：基于高德地图显示景点位置
- 📸 **美图展示**：集成 Unsplash API 获取高质量旅游图片
- 🎯 **智能景点**：自动搜索和推荐目的地周边景点
- 💻 **前后端分离**：现代化的前端 UI 和 RESTful 后端 API

## 项目结构

```
trip-planner/
├── backend/                          # 后端应用
│   ├── app/
│   │   ├── agents/                  # AI 代理模块
│   │   ├── api/                     # API 路由
│   │   ├── services/                # 业务逻辑服务
│   │   ├── models/                  # 数据模型
│   │   └── config.py                # 配置文件
│   ├── requirements.txt              # 依赖清单
│   ├── run.py                        # 启动脚本
│   └── .env.example                  # 环境变量示例
│
├── frontend/                         # 前端应用 (Vue 3 + TypeScript)
│   ├── src/
│   │   ├── views/                   # 页面组件
│   │   ├── services/                # API 服务
│   │   ├── types/                   # TypeScript 类型定义
│   │   └── App.vue                  # 主应用组件
│   ├── package.json                  # NPM 依赖
│   ├── vite.config.ts                # Vite 配置
│   └── .env.example                  # 环境变量示例
│
└── README.md                          # 本文件
```

## 系统要求

### 后端
- Python 3.10+
- pip

### 前端
- Node.js 16+
- npm 或 yarn

## 快速开始

### 1. 后端设置

```bash
# 进入后端目录
cd backend

# 创建虚拟环境
python -m venv venv
# Windows
venv\Scripts\activate
# Linux/Mac
source venv/bin/activate

# 安装依赖
pip install helloagents
# 或安装 requirements.txt 中的所有依赖
pip install -r requirements.txt

# 配置环境变量
cp .env.example .env
# 编辑 .env 文件，填入你的 API 密钥
```

**环境变量配置** (.env)：
```env
# LLM 配置 (必需)
LLM_MODEL_ID=your-model-name
LLM_API_KEY=your-api-key
LLM_BASE_URL=your-api-base-url

# 服务器配置
HOST=0.0.0.0
PORT=8000

# 高德地图 API (必需)
AMAP_API_KEY=your-amap-api-key

# Unsplash API (可选)
UNSPLASH_ACCESS_KEY=your-unsplash-key
UNSPLASH_SECRET_KEY=your-unsplash-secret

# CORS 配置
CORS_ORIGINS=http://localhost:5173,http://localhost:3000
```

**启动后端服务**：
```bash
python run.py
```

后端会在 `http://localhost:8000` 启动

### 2. 前端设置

```bash
# 进入前端目录
cd frontend

# 安装依赖
npm install

# 配置环境变量
cp .env.example .env
# 编辑 .env 文件（如需修改 API 地址）

# 开发模式运行
npm run dev
```

前端会在 `http://localhost:5173` 启动

### 3. 访问应用

打开浏览器访问：`http://localhost:5173`

## API 端点

| 方法 | 端点 | 描述 |
|------|------|------|
| POST | `/api/trip/plan` | 生成旅行计划 |
| GET | `/api/poi/search` | 搜索景点 |
| GET | `/api/map/location` | 获取位置信息 |

## 获取 API 密钥

### 高德地图
1. 访问 [高德地图开放平台](https://lbs.amap.com/)
2. 注册并登录
3. 创建应用获取 API Key

### Unsplash
1. 访问 [Unsplash Developer](https://unsplash.com/developers)
2. 注册并创建应用
3. 获取 Access Key

### LLM 服务
根据你使用的 LLM 服务商获取相应的 API 密钥（如 OpenAI、Anthropic、Moonshot 等）

## 主要依赖

### 后端
- **helloagents**: AI 代理框架
- **fastapi**: 现代 Web 框架
- **pydantic**: 数据验证
- **httpx**: HTTP 客户端

### 前端
- **Vue 3**: 前端框架
- **TypeScript**: 类型安全
- **Vite**: 构建工具
- **Axios**: HTTP 客户端

## 故障排除

**问题：后端无法连接 LLM**
- 检查 `.env` 中的 LLM 配置是否正确
- 验证 API 密钥是否有效

**问题：前端无法连接后端**
- 确保后端服务正在运行 (`http://localhost:8000`)
- 检查 CORS 配置

**问题：高德地图显示异常**
- 确认 AMAP_API_KEY 配置正确
- 检查高德地图 API 的配额限制

## 许可证

MIT

## 贡献

欢迎提交 Issue 和 PR！

## 联系方式

如有问题或建议，请提交 Issue。
