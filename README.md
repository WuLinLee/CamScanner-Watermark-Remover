# CamScanner Watermark Remover — WuLinLee Edition

一个免安装的单文件 HTML 工具，用浏览器批量处理你有权修改的扫描 PDF。

## 使用方式

### 在线网页
打开：<https://wulinlee.github.io/CamScanner-Watermark-Remover/>

### 下载版
从 [Latest Release](https://github.com/WuLinLee/CamScanner-Watermark-Remover/releases/latest) 下载 `index.html` 或 ZIP。打开 `index.html` 即可，不需要 Python、pip、Node.js、npm 或 App。

## 批量处理

1. 一次选择多个 PDF，或把多个 PDF 一起拖入网页。
2. 点击“选择桌面文件夹”。文件夹选择窗口会优先打开桌面，请确认选中“桌面 / Desktop”。
3. 点击“批量去水印并保存到桌面”。
4. 每个结果会保留原文件名并追加时间，例如 `合同_无水印_20261114_193055.pdf`。重复同名文件会额外添加序号，避免覆盖。

桌面直存依赖桌面版 Chrome / Edge 支持的 File System Access API，并需要用户主动授权选择输出文件夹。网页不能在未经授权时自行探测或写入系统桌面。若浏览器不支持此功能，将回退为浏览器普通下载，文件位置取决于浏览器下载设置；此模式无法保证一定落在桌面。

## 隐私

PDF 由浏览器本地读取、处理和写出，不会上传到本项目服务器。页面从 jsDelivr 加载固定版本 pdf-lib 1.17.1 JavaScript 库；这意味着打开网页时需要网络加载处理库，但 PDF 文件本身不会发送出去。下载版 HTML 同样使用这套处理逻辑。

## 适用范围和限制

- 主要识别 CamScanner 常见的独立 PDF XObject 角标（常见资源名 `/X1`，并辅以页面底部小尺寸图形变换检测）。
- 水印若已和整页扫描图像合并，无法无损分离。
- 不同版本或不同导出方式的 PDF 结构可能不同；未检测到对象不代表已成功去除水印。
- 默认同时移除页面注释/链接对象；可能影响 PDF 原有超链接或表单注释。处理结果请检查。
- 工具不会修改原文件。请始终保留备份，并检查文字、表格线、印章和页脚。

## License / attribution

本项目的水印对象识别和 PDF 内容流处理逻辑改编自 [masecla22/CamScanner-Watermark-Remover](https://github.com/masecla22/CamScanner-Watermark-Remover)，原项目使用 MIT License。见 [THIRD-PARTY-NOTICES.md](THIRD-PARTY-NOTICES.md)。

PDF 解析库 [pdf-lib](https://github.com/Hopding/pdf-lib) 使用 MIT License，由页面从 jsDelivr 加载版本 1.17.1。
