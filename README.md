# CamScanner Watermark Remover — WuLinLee Edition

一个**免安装、单 HTML 文件、浏览器本地处理**的 PDF 清理工具。适用于你自己创建、且有权修改的扫描件。

## 直接用（不需要安装环境）

- 在线打开：<https://cdn.jsdelivr.net/gh/WuLinLee/CamScanner-Watermark-Remover@main/index.html>
- 或下载 [index.html](https://github.com/WuLinLee/CamScanner-Watermark-Remover/releases/latest/download/index.html)，用 Chrome / Edge / Firefox 打开。
- 选择 PDF，点“在本机处理 PDF”，再下载处理结果。

不用 Python、pip、Node.js、npm，也不用安装 App。

## 隐私说明

PDF 文件由浏览器的 File API 读取，处理和生成文件都在本机浏览器内存中完成。网页不会将 PDF 内容上传到服务器。页面加载时会从 jsDelivr 加载固定版本的 pdf-lib JavaScript 库；如果希望完全离线，请先将该库另存为本地文件并调整 HTML 的 script 引用（默认发行版需要联网加载这个库）。

## 适用范围和限制

- 主要识别 CamScanner 常见的独立 PDF XObject 角标（常见资源名 `/X1`，并辅以页面底部小尺寸图形变换检测）。
- 水印若已和整页扫描图像合并，无法无损分离。
- 不同版本或不同导出方式的 PDF 结构可能不同；未检测到对象不代表已去除水印。
- 可选清理页面注释对象。启用时可能移除 PDF 原有超链接、表单注释等；不需要时可取消勾选。
- 工具不会修改原文件；请始终检查输出页，特别是表格线、印章和页脚。

## License / attribution

本项目的水印对象识别和 PDF 内容流处理逻辑改编自 [masecla22/CamScanner-Watermark-Remover](https://github.com/masecla22/CamScanner-Watermark-Remover)，原项目使用 MIT License。见 [THIRD-PARTY-NOTICES.md](THIRD-PARTY-NOTICES.md)。

PDF 解析库 [pdf-lib](https://github.com/Hopding/pdf-lib) 使用 MIT License，由页面从 jsDelivr 加载版本 1.17.1。
