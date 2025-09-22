# fund_pdf

[![Python](https://img.shields.io/badge/Python-3.7%2B-blue)](https://www.python.org/)
[![PyQt5](https://img.shields.io/badge/GUI-PyQt5-green)](https://pypi.org/project/PyQt5/)
[![License](https://img.shields.io/badge/License-MIT-yellow)](LICENSE)

一款专业的基金公告PDF文档下载工具，支持自定义存储路径、多线程下载和智能文件管理。

## 功能特性

### 📁 灵活存储管理
- **自定义保存路径**：用户可自由选择PDF文件存储位置
- **智能文件命名**：自动使用基金代码+公告标题命名文件
- **重复文件跳过**：自动检测并跳过已下载的文件

### ⚡ 高效下载体验
- **多线程下载**：后台线程下载，不阻塞UI操作
- **进度实时显示**：直观的进度条和状态提示
- **下载控制**：支持随时开始、暂停和停止下载任务


### 🔧 高级配置选项
- **页面限制**：可设置最大爬取页数（1-100页）
- **延迟调节**：自定义下载延迟时间，防止请求过于频繁
- **请求优化**：随机User-Agent和Referer设置，提高访问成功率

### 📊 详细日志系统
- **实时日志**：显示下载过程中的详细信息
- **状态监控**：实时更新当前操作状态
- **日志管理**：支持清空日志功能

## 安装指南

### 环境要求
- Python 3.7 或更高版本
- 支持的操作系统：Windows 10/11

### 安装步骤

1. **克隆或下载项目文件**
   ```bash
   git clone https://github.com/lather01/fund_pdf.git
   cd fund-pdf
   ```

2. **安装依赖库**
   ```bash
   pip install -r requirements.txt
   ```
   
   或者手动安装：
   ```bash
   pip install PyQt5 requests beautifulsoup4
   ```

3. **运行程序**
   ```bash
   python fund_pdf.py
   ```

## 使用说明

### 基本操作

1. **设置保存路径**
   - 在"保存路径"输入框中直接输入路径，或点击"浏览..."按钮选择文件夹（默认新建fund_pdfs文件夹）
    ![选择文件夹](.\pics\ws_search.png)

2. **配置下载参数**
   - **最大爬取页数**：设置要爬取的页面数量（默认10页）
    [页码调整](.\pics\ws_pages.png)
   - **下载延迟**：设置每个文件下载之间的延迟时间（1-10秒）
    [延迟调整](.\pics\ws_delay.png)
   - **跳过已下载**：勾选此项可避免重复下载已有文件
    [跳过已有文件](.\pics\ws_alreadydown.png)

3. **开始下载**
   - 点击"开始下载"按钮启动下载过程
   - 在日志区域查看实时下载状态
    [下载结束](.\pics\ws_finish.png)

4. **监控下载进度**
   - 进度条显示总体下载进度
   - 状态标签显示当前操作详情
   - 日志窗口记录所有下载活动
    [进程跟踪](.\pics\ws_process.png)

5. **管理下载过程**
   - 点击"停止下载"可随时中断下载
   - 点击"清空日志"可清除日志窗口内容
    [进程跟踪](.\pics\ws_stop.png)

### 文件命名规则

下载的PDF文件按照以下格式命名：
```
{基金代码}_{基金简称}_{公告标题}.pdf
```

示例：
```
110022_易方达消费行业_关于旗下部分基金参加交通银行手机银行申购费率优惠活动的公告.pdf
```

## 技术架构

### 核心组件
- **GUI界面**：基于PyQt5构建的跨平台桌面应用程序
- **网络请求**：使用Requests库处理HTTP请求
- **HTML解析**：BeautifulSoup4解析网页内容
- **多线程处理**：QThread实现后台下载不阻塞UI

### 反爬虫策略
- 随机User-Agent轮换
- 合理的请求延迟
- 模拟浏览器Referer设置
- 连接超时和错误处理机制

## 常见问题

### Q: 下载速度太慢怎么办？
A: 可以适当减少下载延迟设置，但请注意过于频繁的请求可能导致IP被暂时限制。

### Q: 程序无法启动怎么办？
A: 请确保已安装所有依赖库，特别是PyQt5、requests和beautifulsoup4。

### Q: 下载的文件损坏怎么办？
A: 程序会自动删除下载不完整的文件，您可以重新启动下载任务。

### Q: 如何批量下载特定类型的公告？
A: 当前版本支持下载所有类型的公告，未来版本将增加筛选功能。

## 更新日志

### v1.0.0 (2023-10-15)
- 初始版本发布
- 实现基本PDF下载功能
- 添加GUI用户界面
- 支持自定义存储路径

## 免责声明

本工具仅用于技术研究和学习目的，请勿用于任何商业用途或侵犯版权的行为。使用者应对自己的行为负责，开发者不承担任何法律责任。

## 开源协议

本项目采用 MIT 协议开源，详情请参阅 [LICENSE](LICENSE) 文件。

## 贡献指南

欢迎提交Issue和Pull Request来帮助改进这个项目。

1. Fork 本项目
2. 创建特性分支 (`git checkout -b feature/AmazingFeature`)
3. 提交更改 (`git commit -m 'Add some AmazingFeature'`)
4. 推送到分支 (`git push origin feature/AmazingFeature`)
5. 开启Pull Request

## 支持与联系

如果您遇到任何问题或有建议，请通过以下方式联系：

- 提交 [GitHub Issue](https://github.com/lather01/fund_pdf/issues)
- 发送邮件至：lather.wzww@gmail.com

---

**注意**：请遵守相关网站的使用条款，合理使用本工具。
