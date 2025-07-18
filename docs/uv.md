uv 备忘清单
===

一个用 Rust 编写的极快的 Python 包和项目管理工具

安装
---

### 使用独立安装程序安装

#### macOS or Linux

```sh
curl -LsSf https://astral.sh/uv/install.sh | sh
```

#### Windows

```sh
powershell -ExecutionPolicy ByPass -c "irm https://astral.sh/uv/install.ps1 | iex"
```

### 通过PyPI

```sh
# pip
pip install uv
```

```sh
# pipx
pipx install uv
```

入门
---

### 创建新项目
<!--rehype:wrap-class=row-span-2-->
```sh
# 创建一个目录作为项目的根目录
uv init project_name
```

```sh
# 将当前目录作为项目的根目录
uv init
```

#### 项目的结构

```sh
.
├── .venv # 项目的虚拟环境
│   ├── bin
│   ├── lib
│   └── pyvenv.cfg
├── .python-version # 项目的 Python 版本
├── README.md
├── main.py
├── pyproject.toml # 项目的元数据
└── uv.lock # 项目的锁定文件, 用于锁定依赖版本,不应手动编辑
```

### 管理项目依赖
<!--rehype:wrap-class=row-span-2-->
#### 添加依赖

```sh
uv add requests
```

#### 指定依赖版本或替代来源

```sh
# 指定版本
uv add 'requests==2.28.1'

# 指定来源
uv add git+https://github.com/psf/requests
```

#### 从`requirements.txt`迁移

```sh
uv add -r requirements.txt
```

#### 删除一个包

```sh
uv remove requests
```

#### 升级一个包

```sh
uv lock --upgrade-package requests
```

### 运行脚本

指定脚本运行

```sh
uv run main.py
```

指定Python版本运行

```sh
uv run --python 3.10 main.py
```

### 构建项目

```sh
uv build
```

构建结果存储在`dist`目录下
