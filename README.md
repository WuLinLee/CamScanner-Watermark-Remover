# CamScanner Watermark Remover — WuLinLee Edition

免安装的单文件 HTML 工具，在浏览器本机批量处理你有权修改的扫描 PDF。

## 直接使用

- 在线网页：<https://wulinlee.github.io/CamScanner-Watermark-Remover/>
- 下载版：进入 [Latest Release](https://github.com/WuLinLee/CamScanner-Watermark-Remover/releases/latest)，下载 `index.html` 或 ZIP，打开 `index.html` 即可。
- 不需要 Python、pip、Node.js、npm 或 App。

## 批量处理和自动保存到桌面

1. 一次选择多份 PDF，或把一批 PDF 一起拖进网页。
2. 点击“批量去水印并自动下载”。
3. 网页逐个处理并自动触发下载。文件名保留原名并添加时间后缀，例如 `合同_无水印_20261114_193055.pdf`；同批次同名文件会增加序号，避免名称冲突。
4. **要让文件自动落到桌面，只需在浏览器中设置一次默认下载位置为“桌面 / Desktop”，并关闭“下载前询问每个文件的保存位置”。** Chrome 可打开 `chrome://settings/downloads` 设置。首次批量下载时，如果浏览器询问是否允许网站下载多个文件，请选择允许。

网页不能绕过浏览器权限自行查找或写入操作系统桌面。它会使用浏览器默认下载目录；将默认目录设为桌面后，网页版和 Release 下载版都会自动下载到桌面。若使用手机浏览器或不支持多文件下载的浏览器，则保存位置由系统/浏览器决定，不能保证是电脑桌面。

## 隐私

PDF 文件由浏览器本地读取、处理和生成，不会上传到本项目服务器。页面会从 jsDelivr 加载固定版本 pdf-lib 1.17.1 JavaScript 库；这需要网络加载脚本，但不会上传所选 PDF。网页版与 Release 下载版使用完全相同的 `index.html`。

## 适用范围和限制

- 主要识别 CamScanner 常见的独立 PDF XObject 角标（常见资源名 `/X1`，并辅以页面底部小尺寸图形变换检测）。
- 水印若已和整页扫描图像合并，无法无损分离。
- 不同版本或不同导出方式的 PDF 结构可能不同；未检测到对象不代表已成功去除水印。
- 默认同时移除页面注释/链接对象；可能影响 PDF 原有超链接或表单注释。可在页面取消勾选。
- 工具不会修改原文件。请保留备份，并检查文字、表格线、印章和页脚。

## License / attribution

本项目的水印对象识别和 PDF 内容流处理逻辑改编自 [masecla22/CamScanner-Watermark-Remover](https://github.com/masecla22/CamScanner-Watermark-Remover)，原项目使用 MIT License。见 [THIRD-PARTY-NOTICES.md](THIRD-PARTY-NOTICES.md)。

PDF 解析库 [pdf-lib](https://github.com/Hopding/pdf-lib) 使用 MIT License，由页面从 jsDelivr 加载版本 1.17.1。
