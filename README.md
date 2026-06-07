# Django Learning Log

这是一个基于 Django 的学习日志 Web 应用。用户可以注册、登录，创建学习主题，并在每个主题下记录学习笔记。项目适合作为 Django 入门练习，覆盖了模型、视图、模板、表单、用户认证和权限控制等基础功能。

## 功能

- 用户注册、登录和退出
- 创建学习主题 Topic
- 查看当前用户自己的主题列表
- 在主题下新增学习记录 Entry
- 编辑已有学习记录
- 基于登录用户进行数据隔离，避免访问其他用户的主题
- 使用 SQLite 作为本地开发数据库

## 技术栈

- Python
- Django 4.2.7
- SQLite
- HTML templates
- Django authentication

## 目录结构

```text
Diango-Project/
└── learning_log/
    ├── learning_log/       # Django 项目配置
    ├── learning_logs/      # 学习日志核心 app
    ├── users/              # 用户注册、登录、退出 app
    ├── manage.py
    └── db.sqlite3
```

核心文件：

- `learning_logs/models.py`：定义 `Topic` 和 `Entry` 模型
- `learning_logs/views.py`：主题和日志的展示、创建、编辑逻辑
- `learning_logs/forms.py`：主题和日志表单
- `users/views.py`：用户注册和退出逻辑
- `users/urls.py`：用户相关路由

## 如何运行

1. 克隆仓库：

```bash
git clone https://github.com/aqwddda/Diango-Project.git
cd Diango-Project/learning_log
```

2. 创建并激活虚拟环境：

```bash
python -m venv .venv
.venv\Scripts\activate
```

3. 安装依赖：

```bash
pip install django
```

4. 执行数据库迁移：

```bash
python manage.py migrate
```

5. 启动开发服务器：

```bash
python manage.py runserver
```

6. 打开浏览器访问：

```text
http://127.0.0.1:8000/
```

## 页面路由

- `/`：首页
- `/topics/`：主题列表
- `/topics/<topic_id>/`：主题详情
- `/new_topic/`：新增主题
- `/new_entry/<topic_id>/`：新增学习记录
- `/edit_entry/<entry_id>/`：编辑学习记录
- `/users/register/`：注册
- `/users/login/`：登录
- `/users/logout/`：退出

## 说明

这是一个学习型 Django 项目，主要用于练习 Web 开发基础功能。当前仓库中包含本地开发产生的数据库和环境文件，后续可以进一步整理 `.gitignore`，移除虚拟环境和缓存文件，使仓库更适合公开展示。
