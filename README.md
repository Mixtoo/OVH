# 🚀 启动说明

## 📦 项目已完全清理

所有缓存、日志、依赖已清理，项目处于首次缺省状态。

---

## 🐳 Docker 部署（推荐）

### 一键启动

```bash
docker-compose up -d --build
```

### 访问应用

- **前端：** http://localhost:8080
- **后端：** http://localhost:5000

### 配置

访问：http://localhost:8080/settings

1. 输入网站安全密钥（默认：`ovh-phantom-sniper-2024-secret-key`）
2. 填写 OVH API 凭据
3. 保存

**完成！** ✅

---

## 💻 本地开发

### 1. 安装依赖

```bash
# 后端
cd backend
pip install -r requirements.txt

# 前端
cd ..
npm install
```

### 2. 启动服务

```bash
# 后端（终端1）
cd backend
python app.py

# 前端（终端2）
npm run dev
```

### 3. 访问

- **前端：** http://localhost:8080
- **后端：** http://localhost:5000

---

## 🔑 默认配置

**backend/.env：**
```env
API_SECRET_KEY=ovh-phantom-sniper-2024-secret-key
PORT=5000
DEBUG=false
ENABLE_API_KEY_AUTH=true
```

⚠️ **生产环境请修改 API_SECRET_KEY！**

---

## 📊 端口说明

| 服务 | 端口 | 说明 |
|------|------|------|
| 前端 | 8080 | 直接访问，无需代理 |
| 后端 | 5000 | API 服务 |

**前端直接连接后端 5000 端口** - 简单直接！

---

## 🎯 快速命令

```bash
# Docker 启动
docker-compose up -d --build

# Docker 停止
docker-compose down

# Docker 查看日志
docker-compose logs -f

# 本地开发
cd backend && python app.py
npm run dev
```

---

**选择一种方式启动即可！** ✨




# 🐳 Docker 使用说明

## 🚀 启动

```bash
docker-compose up -d --build
```

---

## 🌐 访问

**前端地址：** http://localhost:8080

**说明：**
- 前端运行在 **8080** 端口
- 后端运行在 **5000** 端口（前端自动连接）

---

## ⚙️ 配置

### 修改配置文件

直接编辑：`backend/.env`

```env
API_SECRET_KEY=123456
PORT=5000
DEBUG=false
ENABLE_API_KEY_AUTH=true
```

### 使配置生效

```bash
docker-compose restart
```

---

## 🔧 修改前端端口

**文件：** `vite.config.ts` 第 10 行

```typescript
server: {
  port: 8080,  // 改成其他端口，如 3000, 5173 等
}
```

修改后重新构建：
```bash
docker-compose up -d --build
```

---

## 📋 常用命令

```bash
# 启动
docker-compose up -d

# 停止
docker-compose stop

# 重启
docker-compose restart

# 查看日志
docker-compose logs -f

# 删除容器
docker-compose down
```

---

## 📁 文件位置

所有文件都在宿主机（您的项目目录）：

```
backend/
├── .env          ← 修改配置
├── data/         ← 数据文件
├── logs/         ← 日志文件
└── cache/        ← 缓存文件
```

**直接修改，重启容器生效！** ✅

---

## 🎯 完整流程

```bash
# 1. 启动容器
docker-compose up -d --build

# 2. 访问前端
http://localhost:8080

# 3. 配置密钥
访问设置页面配置 API 密钥

# 4. 修改配置（如需要）
编辑 backend/.env
docker-compose restart
```

**就这么简单！** 🎉
