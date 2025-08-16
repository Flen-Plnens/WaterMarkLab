# WaterMarkLab

[![English](README.md) | [![中文](README_zh.md)

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)
[![Python Version](https://img.shields.io/badge/python-3.9+-blue.svg)](https://www.python.org/downloads/)

一个轻量级的单文件 Flask Web 应用，用于学习和实验 LSB（最低有效位）隐写术与基于 DCT 的渐显式视觉水印技术。

该工具主要为教育和实验目的而设计，提供了一个用户友好的界面，以帮助理解数字水印的基础知识。它对 Termux 友好，方便在移动设备上部署。

![WaterMarkLab UI 截图](https://user-images.githubusercontent.com/YOUR_USER_ID/YOUR_REPO_ID/...)
*(建议：请将此处的链接替换为你应用的真实 UI 截图)*

---

### 功能特性

* **双重水印技术**:
    * **LSB 隐写水印**: 通过修改图像像素的最低有效位来嵌入不可见的隐性数据（文本或图片）。
    * **DCT 渐显水印**: 在图像的频域中添加一个半可见水印，该水印在经过 JPEG 压缩或缩放后会“浮现”出来。
* **丰富的参数控制**:
    * **预设方案**: 提供 `stealth` (隐匿)、`balanced` (均衡) 和 `robust` (鲁棒) 三种预设，方便快速配置。
    * **LSB 位数 (bpc)**: 可选择每个颜色通道使用 1 或 2 个最低有效位进行嵌入。
    * **冗余度**: 将每个数据位重复嵌入多次，以抵抗数据损坏。
    * **随机散布**: 将水印数据随机分布在整张图片中，以抵御剪裁攻击。
    * **通道选择**: 可自由选择用于嵌入的颜色通道 (R, G, B)。
* **直观的 Web 界面**:
    * 简洁的单页 UI，支持浅色和深色主题。
    * 同时支持文本水印和图片水印。
    * 提供实时的 JPEG 质量预览，以模拟压缩效果。
    * 内置水印检测与提取功能。
* **独立且便携**:
    * 由单个 Python 文件构成，依赖项极少。
    * 包含临时文件自动清理机制。

### 快速开始

#### 环境要求

- 推荐使用 Python 3.9 或更高版本。
- `pip` 包管理器。

#### 安装

1.  克隆本仓库：
    ```bash
    git clone [https://github.com/Flen-Plnens/WaterMarkLab.git](https://github.com/Flen-Plnens/WaterMarkLab.git)
    cd WaterMarkLab
    ```

2.  安装所需依赖：
    ```bash
    pip install --user Flask Pillow opencv-python-headless numpy
    ```

3.  运行应用：
    ```bash
    python app.py
    ```
    应用将启动在 `http://127.0.0.1:5000`。如果 5000 端口被占用，程序会自动尝试 5001-5010 端口。

### 使用方法

1.  **打开**你的浏览器并访问 `http://127.0.0.1:5000`。
2.  **上传载体图片**: 点击“选择原图文件...”来选择你想要添加水印的图片。
3.  **配置水印**:
    * 选择“水印类型”（`文本`或`图片`）。
    * 输入你的文本内容，或上传一张水印图片。
    * 选择一个“预设”（推荐从 `balanced` 开始）。
    * 根据需要微调下方的详细参数（如 LSB 位数、冗余度等）。
4.  **嵌入**: 点击“嵌入”按钮。处理后的图片和自检结果将显示在右侧。
5.  **检测**: 如需提取水印，请上传一张疑似包含水印的图片，然后点击“检测/提取”按钮。

### 许可证

本项目基于 MIT 许可证开源。详情请见 [LICENSE](LICENSE) 文件。

### 致谢

* 项目的前端界面由自定义的 `subtlekit.css` 框架构建。
