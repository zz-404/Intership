# miniconda
```
Miniconda 的核心价值：
环境隔离：为每个项目创建独立 “环境”，比如给 CV 项目建cv_study环境，给 Transformer 项目建transformer_study环境，环境间互不干扰；
一键配置：快速安装指定 Python 版本，以及 NumPy、PyTorch 等依赖，还能导出环境配置（比如把你ai_study环境的所有包和版本记录下来，发给别人能一键复现）；
轻量高效：只包含最核心的工具（conda 环境管理器 + Python），不像 Anaconda 预装了一大堆用不上的包，节省空间且启动快。

二、关键概念：你需要知道的 3 个核心操作

Miniconda 的核心是 “conda 命令”，日常用得最多的就 3 个，你之前已经用过部分：

1. 创建环境：conda create -n ai_study python=3.9
意思是：新建一个名叫ai_study的环境，指定 Python 版本 3.9（适配大部分 AI 包）；

2. 激活环境：conda activate ai_study
激活后，你在终端安装的所有包（比如pip install torch）都会存到这个环境里，不会影响其他环境；

3. 安装 / 卸载包：
用conda install numpy pandas（适合安装系统依赖类包）；
用pip install torch（适合安装 AI 框架，和 conda 兼容，互不冲突）；
卸载用conda remove 包名或pip uninstall 包名。
```
