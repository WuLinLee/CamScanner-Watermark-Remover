# CamScanner Watermark Remover — WuLinLee Edition

免安装的单文件 HTML 工具，在浏览器本机批量处理你有权修改的扫描 PDF。

## 直接使用

- 在线网页：<https://wulinlee.github.io/CamScanner-Watermark-Remover/>
- 下载版：进入 [Latest Release](https://github.com/WuLinLee/CamScanner-Watermark-Remover/releases/latest)，下载 `index.html` 或 ZIP，打开 `index.html` 即可。
- 不需要 Python、pip、Node.js、npm 或 App。

## 批量处理和自动下载

1. 一次选择多份 PDF，或把一批 PDF 一起拖进网页。
2. 点击“批量去水印并自动下载”。
3. 网页逐个处理并自动触发下载，结果进入浏览器默认的“下载”文件夹。文件名保留原名并添加时间后缀，例如 `合同_无水印_20261114_193055.pdf`；同批次同名文件会增加序号，避免名称冲突。
4. 首次批量下载时，如果浏览器询问是否允许网站下载多个文件，请选择允许。

默认启用右下角文字标识清理：工具读取字体的 `ToUnicode` 映射，并尝试从页面主内容流及 Form XObject 内容流中直接删除可确认属于“扫描全能王 创建”的文字绘制指令，不会覆盖或涂白页面。它可匹配被拆分到多个连续 `Tj/TJ` 指令（包括相邻文字块）的水印。为避免误删正文，只删除连续文字指令完整组成水印短语的情况；若字体没有可用的 Unicode 映射、文字编码特殊或内容结构无法识别，则保留原文并在结果中提示未识别。

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
