# 虚幻引擎中文文档

## 使用方法
1. 克隆仓库
```shell
git clone https://github.com/OpenHUTB/engine_doc.git
```
2. 从 [链接](https://pan.baidu.com/s/1XmbdG9jy7gOWjbD8Km9FWA?pwd=hutb) 下载依赖图片包`Images.zip`，解压到项目主目录；
3. 使用浏览器打开文件`zh-CN/index.html`。

## 构建步骤
1. 使用 [`HTTrack`](https://www.httrack.com/) 从 [链接](https://docs.unrealengine.com/4.26/zh-CN/) 中下载所有网页文件（比如设置项目名为：`engine_doc`）；
2. 仅使用`engine_doc\docs.unrealengine.com\4.26`中的文件，并将`zh-CN`中所有网页文件中包含`.webp`的文本替换为`.jpg`（比如使用Pycharm菜单中`Edit->Find->Replace in Files`工具）。


## 自定义方法

* 所有文件字符串的替換

    点击pycharm菜单的`Edit -> File -> Replace In Files..`，填写替换前和替换后的字符串。

* 删除页脚

    使用浏览器打开页面，按`F12`键打开开发者工具，按`Ctrl+Shift+C`选择页脚，右键删除对应的元素（刷新后仍然不变）；应该删除所有页面的`<div id="footer"></div>`。

