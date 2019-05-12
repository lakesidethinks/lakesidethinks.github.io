---
layout: post
title: "本地转换中英文扫描版PDF为可搜索文件"
tagline: ""
description: ""
category: 博客
tags: [ocrmypdf, 读书技巧]
last_updated:
---

我终于找到了一个可以本地把扫描版的中文PDF变成可搜索的PDF的命令行工作流程。具体方式为安装支持中文包的ocrmypdf这一开源软件。

## 安装流程

以下为在Mac上配置的流程。其他系统可以参考[官方帮助网页](https://ocrmypdf.readthedocs.io/en/latest/installation.html#macos-all-languages)：

- 安装Brew
- 安装翻译引擎和全部语言包
```bash
brew install tesseract --with-all-languages
brew install ghostscript
brew install poppler
brew install imagemagick
```
- 安装ocrmypdf
```bash
brew install ocrmypdf
```

## 使用范例

### 官方使用范例
```bash
ocrmypdf                      # it's a scriptable command line program
   -l eng+fra                 # it supports multiple languages
   --rotate-pages             # it can fix pages that are misrotated
   --deskew                   # it can deskew crooked PDFs!
   --title "My PDF"           # it can change output metadata
   --jobs 4                   # it uses multiple cores by default
   --output-type pdfa         # it produces PDF/A by default
   input_scanned.pdf          # takes PDF input (or images)
   output_searchable.pdf      # produces validated PDF output
```

### 使用ocrmypdf扫描中英文混排的PDF
```bash
ocrmypdf -l eng+chi_sim input.pdf output.pdf
```
其中中文有四个选项,分别为
- chi_sim 横排简体中文
- chi_sim_vert 竖排简体中文
- chi_tra 横排繁体中文
- chi_tra_vert 竖排繁体中文
把英文放在中文前面应该是会比反过来放的效果更好。

### 把PDF的每一页分割为单页PDF
```bash
pdfseparate cn1.pdf -f 1 -l 10 out_%d.pdf
```
-f 指定分割开始的第一页， -l 指定分割的最后一页。

## 高级功能
根据ocrmypdf的[pip页面](https://pypi.org/project/pypdfocr/)，ocrmypdf还原生支持许多高级功能，比如监控并自动翻译指定目录下的PDF文件，自动把OCR完成的PDF移动到其他目录甚至是上传到Evernote。
