# 虚幻引擎中文文档

## 使用方法
1. 克隆仓库和图片依赖
```shell
git clone https://github.com/OpenHUTB/engine_doc.git
cd engine_doc
# 备份图片（Images.zip）：https://pan.baidu.com/s/1XmbdG9jy7gOWjbD8Km9FWA?pwd=hutb
git clone --recursive https://github.com/OpenHUTB/Images.git
```
2. 使用浏览器打开文件`zh-CN/index.html`。

## 构建步骤
1. 使用 [`HTTrack`](https://www.httrack.com/) 从 [链接](https://docs.unrealengine.com/4.26/zh-CN/) 中下载所有网页文件（比如设置项目名为：`engine_doc`）；
2. 仅使用`engine_doc\docs.unrealengine.com\4.26`中的文件，并将`zh-CN`中所有网页文件中包含`.webp`的文本替换为`.jpg`（比如使用Pycharm菜单中`Edit->Find->Replace in Files`工具）。


## 自定义方法

* 所有文件字符串的替換

    点击pycharm菜单的`Edit -> Find -> Replace In Files..`，填写替换前和替换后的字符串。


* 删除页脚

    使用浏览器打开页面，按`F12`键打开开发者工具，按`Ctrl+Shift+C`选择页脚，右键删除对应的元素（刷新后仍然不变）；应该删除所有页面的`<div id="footer"></div>`。


## 修复页面

* 替换失效的链接（目录不存在，显示红色）
    
    调整前：
    ```html
    <div class="errorhighlight" id="Error20">[编辑Actor属性](Basics/Actors/DetailsPanel/index.html)</div>    
    ```
    调整后（**相对路径** vs 绝对路径）：
    ```html
    <a id="content_link" href="../../Basics/HowTo/DetailsPanel/index.html" ><span>编辑Actor属性</span></a>
    <a id="content_link" href="https://openhutb.github.io/engine_doc/zh-CN/Basics/HowTo/DetailsPanel/index.html" ><span>编辑Actor属性</span></a>    
    ```

* 替换失效的图片（Images 目录中不存在指定图片）
    调整前
    ```html
    <p><div class="errorhighlight" id="Error6">[![虚幻引擎4中的蓝图编辑器](ue4-blueprint-editor.png "Blueprint Editor inside Unreal Engine 4.")(w:600)](ue4-blueprint-editor.png)</div></p>
    ```
    搜索`)(w:600)](`、`点击查看大图`，参考[原始文档](https://dev.epicgames.com/documentation/unreal-engine/tools-and-editors?application_version=4.27)替换为：
    ```html
	<p>
		<picture>
		<source data-srcset="./../../../Images/Basics/ToolsAndEditors/ue4-blueprint-editor.png">
		<img class="  lazyload" alt="Finished.png" data-src="./../../../Images/Basics/ToolsAndEditors/ue4-blueprint-editor.png" />
		</picture>
	</p>
    ```
    将指定图片添加到 [Images](https://github.com/OpenHUTB/Images) 仓库中。


## 引用

* [engine_doc/Images的图床](https://github.com/OpenHUTB/Images)
* [engine_doc/Images/Resources的图床](https://github.com/OpenHUTB/Resources)
* [engine_doc/Images/RenderingAndGraphics的图床](https://github.com/OpenHUTB/RenderingAndGraphics)
