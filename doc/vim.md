# Vim 使用简介

![](http://blog.bestswifter.com/WX20180110-204528@2x.png)

基本效果如图所示。

Leader 键是 `空格 space`, NerdTree 和 Denite 专用的 Leader 键是 `;`

## Window 和 Buffer

首先要明确 Window 和 Buffer 的概念，和编辑器无关的外部窗口，比如 NerdTree
这样的文件列表属于 Window。而打开的多个文件，每个都是一个 Buffer。

`<Tab>` 键可以在多个 Window 间切换，切记不要使用鼠标或者触摸板。

如果 Window 过多，可以按下 `-`，将会弹出所有 Window
的缩写，输入对应的字母就可以快速切换了

`g0` 表示前往第一个 Buffer，`g$` 表示前往最后一个 Buffer。

`gr` 表示前一个 Buffer，`gn` 表示后一个 Buffer

## 常见插件的用法

受篇幅所限，这里只介绍一些 Life-Changing 系列的插件

### easymotion

如果只能安装一个 vim 插件，我会选择它，因为原生的 vim
虽然有很多快速的跳转方式，但依然不够快，而 easymotion 则是一个能让
光标移动速度跟上你手速的神奇。

虽然 easymotion 有很多配置，但我一般只有用到两个：

1. `sw`，全局以单词为单位跳转，
   屏幕内的每个单词都会显示高亮的缩写，只要输入缩写就可以快速跳转了。
2. `sl`，在行内跳转， 速度更快，更准确，但使用场景肯定略小一些

### NerdTree

在这份配置中，NerdTree 会在打开文件时自动打开，在关闭最后一个文件时自动关闭，也可以用 `;a` 手动打开

在 NerdTree 中，使用 `hjkl` 操作，`jk` 表示上下移动，`hl`
表示展开或者折叠文件夹。

### TagBar

这个插件依赖于 ctags，在配置脚本中会自动安装，否则需要使用下面的命令来安装：

```shell
brew install --HEAD universal-ctags/universal-ctags/universal-ctags
```

把我 TagBar 配置为启动时自动打开，手动打开的快捷键是 `<leader> + o`
