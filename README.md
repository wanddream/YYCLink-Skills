# YYCLink AI Skills

YYCLink 的个人 AI Skill 集合，用于 Claude Code 等 AI 编程助手。

> 📋 **本仓库是技能索引中心**，每个技能都是独立仓库，可单独下载使用。

## 🎯 我的 Skills

### 元技能

| Skill | 说明 | 适用场景 | GitHub |
|-------|------|----------|--------|
| **skill-dev-driver** ⭐ | 开发驾驶元技能 - 项目上下文管理/技能调度 | 所有项目的开发驾驶 | [GitHub](https://github.com/wanddream/skill-dev-driver) |

### 领域技能

| Skill | 说明 | 适用场景 | GitHub |
|-------|------|----------|--------|
| **skill-blender-industrial** 🆕 | Blender 工业产品建模 - 通过 MCP 与 Blender 通信 | 3D 建模/工业产品设计/3D 打印 | [GitHub](https://github.com/wanddream/skill-blender-industrial) |
| skill-miniprogram-ecosystem | 小程序开发生态 | 微信/抖音/支付宝小程序开发 | [GitHub](https://github.com/wanddream/skill-miniprogram-ecosystem) |
| skill-thesis-writer | 论文写作助手 | 学术论文写作 | [GitHub](https://github.com/wanddream/skill-thesis-writer) |
| skill-product-manager | 产品经理拷打 | 产品方案评审/从 0 到 1 打磨 | [GitHub](https://github.com/wanddream/skill-product-manager) |

## 🚀 快速开始

### 方式一：一键下载所有 Skills（推荐）

**Windows 用户：**

直接双击 **`run.bat`** 即可自动下载/更新所有 Skills。

> 如果双击没反应，可能是 PowerShell 执行策略限制，右键 `install.ps1` → 使用 PowerShell 运行。

**Linux/Mac:**
```bash
# 手动克隆
git clone https://github.com/wanddream/skill-miniprogram-ecosystem.git
git clone https://github.com/wanddream/skill-thesis-writer.git
```

### 方式二：手动克隆单个 Skill

```bash
# 开发驾驶（元技能）
git clone https://github.com/wanddream/skill-dev-driver.git

# Blender 工业产品建模
git clone https://github.com/wanddream/skill-blender-industrial.git

# 小程序开发生态
git clone https://github.com/wanddream/skill-miniprogram-ecosystem.git

# 论文写作助手
git clone https://github.com/wanddream/skill-thesis-writer.git

# 产品经理拷打
git clone https://github.com/wanddream/skill-product-manager.git
```

### 方式三：让 AI 读取远程 SKILL.md

告诉 AI：
> "读取 https://github.com/wanddream/skill-xxx/raw/main/SKILL.md"

AI 会自动获取技能指令，无需下载到本地。

## 📁 目录结构

```
YYCLink-Skills/
├── README.md              # 本文件 - 技能总览
├── install.ps1            # Windows 一键下载/更新脚本
├── run.bat                # 双击运行入口
├── .gitignore             # 忽略下载的 skill-*/ 文件夹
├── skill-dev-driver/      # 开发驾驶元技能（下载后）
├── skill-blender-industrial/    # Blender 工业产品建模（下载后）
├── skill-miniprogram-ecosystem/ # 小程序技能（下载后）
├── skill-thesis-writer/         # 论文技能（下载后）
└── skill-product-manager/       # 产品经理拷打（下载后）
```

## 🔄 更新所有 Skills

直接双击 **`run.bat`**，脚本会自动检测本地已存在的技能并执行 `git pull` 更新。

## ➕ 如何添加新 Skill

本仓库支持两种方式添加新技能：

---

### 方式 A：从零创建新技能（独立仓库）

适用于创建全新的技能仓库。

#### 第 1 步：创建新技能仓库

1. 在 GitHub 创建新仓库，命名格式：`skill-<功能名>`
   - 例如：`skill-web-dev`、`skill-python-ml`

2. 本地创建技能结构：
```
skill-xxx/
├── SKILL.md          # 核心技能文件（必填）
├── README.md         # 技能说明文档
├── examples/         # 示例代码（可选）
└── .gitignore
```

#### 第 2 步：编写 SKILL.md

`SKILL.md` 是 AI 读取的核心文件，告诉 AI 如何使用这个技能。

**⚠️ 重要：必须包含 `name` 字段**，否则 CodeBuddy 无法正确识别技能名称：

```markdown
---
name: skill-xxx
description: 技能描述
triggerKeywords: ["关键词 1", "关键词 2"]
author: YourName
version: 1.0.0
---

# Skill: 技能名称

## 描述
这个技能是做什么的...

## 触发词
当用户说以下关键词时触发此技能：
- "关键词 1"
- "关键词 2"

## 指令
当技能被触发时，AI 应该：
1. 第一步做什么
2. 第二步做什么

## 示例
用户：xxx
AI：xxx
```

#### 第 3 步：提交到 GitHub

```bash
git add .
git commit -m "init: 创建 skill-xxx 技能"
git push -u origin main
```

#### 第 4 步：在 YYCLink-Skills 索引仓库中注册

> 切换到 `YYCLink-Skills` 仓库目录，执行以下操作：

1. 克隆新技能到本地：
```bash
git clone https://github.com/username/skill-xxx.git
```

2. 更新 `install.ps1` - 添加下载配置
3. 更新 `README.md` - 添加技能到表格和目录结构
4. 更新 `skill-dev-driver/skill-index.json` - 注册技能路由
5. 提交并推送：
```bash
git add .
git commit -m "feat: 添加新技能 skill-xxx"
git push
```

---

### 方式 B：复制现有技能文件夹后初始化

适用于已将新技能文件夹复制到 `YYCLink-Skills/` 目录下的情况。

#### 前置条件

你已经把新技能文件夹 `skill-xxx` 复制到了 `YYCLink-Skills/` 目录下：

```
YYCLink-Skills/
├── skill-xxx/    ← 新复制的技能文件夹
├── skill-dev-driver/
├── skill-blender-industrial/
└── ...
```

#### 步骤 1：检查新技能文件夹结构

确认以下文件存在：
- ✅ `skill-xxx/SKILL.md`（核心技能文件，必须包含 `name` 字段）
- ✅ `skill-xxx/README.md`（技能说明文档）
- ✅ `skill-xxx/.gitignore`

#### 步骤 2：告诉 AI 初始化新技能

对 AI 说：**"我添加了一个新技能 skill-xxx，请帮我初始化"**

AI 将自动执行以下操作：

| 序号 | 操作 | 文件 | 说明 |
|------|------|------|------|
| 1 | 更新下载配置 | `install.ps1` | 在 `$repos` 数组中添加新技能 |
| 2 | 更新技能表格 | `README.md` | 在"我的 Skills"表格中添加新行 |
| 3 | 更新目录结构 | `README.md` | 在目录树中添加新技能 |
| 4 | 更新克隆命令 | `README.md` | 在"手动克隆单个 Skill"中添加命令 |
| 5 | 注册技能路由 | `skill-dev-driver/skill-index.json` | 在 `externalSkills` 中添加配置 |

#### 步骤 3：验证和提交

AI 完成初始化后，检查更改是否正确：

```bash
git status
git add .
git commit -m "feat: 添加新技能 skill-xxx"
git push
```

---

### 完整示例流程

```bash
# ====== 方式 A：从零创建 ======
# 1. 创建新仓库
mkdir skill-web-dev
cd skill-web-dev
git init

# 2. 创建 SKILL.md
cat > SKILL.md << 'EOF'
---
name: skill-web-dev
description: Web 开发指南
triggerKeywords: ["web", "前端", "后端"]
author: YYCLink
version: 1.0.0
---

# Skill: Web 开发

## 描述
前端和后端开发最佳实践

## 触发词
- "web 开发"
- "前端"
- "后端"

## 指令
1. 询问用户具体需求
2. 提供技术方案
EOF

# 3. 提交到 GitHub
git add .
git commit -m "init"
git remote add origin https://github.com/username/skill-web-dev.git
git push -u origin main

# 4. 在索引仓库更新配置
cd ../YYCLink-Skills
git clone https://github.com/username/skill-web-dev.git
# 编辑 install.ps1、README.md、skill-index.json
git add .
git commit -m "feat: 添加 skill-web-dev"
git push

# ====== 方式 B：复制后初始化 ======
# 1. 复制技能文件夹到 YYCLink-Skills 目录
cp -r ../skill-web-dev ./YYCLink-Skills/

# 2. 告诉 AI 初始化
# "我添加了一个新技能 skill-web-dev，请帮我初始化"

# 3. AI 自动完成后，验证并提交
git add .
git commit -m "feat: 添加 skill-web-dev"
git push
```

## 🔧 在 CodeBuddy 中使用

### 导入方式（推荐「用户 Skill」）

打开 CodeBuddy → 设置 → 技能 → 导入 Skill

| 类型 | 适用场景 | 特点 |
|------|----------|------|
| **用户 Skill** ⭐ | 个人通用技能 | 跨项目全局可用，切换项目自动继承 |
| 项目 Skill | 项目专属规范 | 仅当前项目有效，换项目需重新导入 |

> 💡 **建议**：个人开发的技能一律作为「用户 Skill」导入，这样在任何项目中都能使用，无需重复配置。

### 使用步骤

1. **下载 Skill**：通过本仓库的 `run.bat` 一键下载所有技能
2. **导入 CodeBuddy**：设置 → 技能 → 导入 Skill → 选择下载好的 `SKILL.md` 文件
3. **选择「用户 Skill」**：确保导入时选择「用户 Skill」类型
4. **开启使用**：在技能列表中开启对应的技能开关即可

## 🤖 AI 如何使用 Skills

### 方法 1：读取本地 SKILL.md（如果已下载）
```
用户：使用小程序技能
AI：读取 skill-miniprogram-ecosystem/SKILL.md 获取指令
```

### 方法 2：读取远程 SKILL.md（无需下载）
```
用户：使用小程序技能
AI：通过 HTTP 读取远程 SKILL.md 内容
```

---

**作者**: YYCLink  
**协议**: MIT License
