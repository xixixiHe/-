# ECNU-本科毕业论文TeX模板


- 本模板提倡模块化的论文写作方式。所有tex文件，最终都会汇入到`main.tex`中进行编译。

## 1. 文件及说明

### `main.tex`

- 本模板的核心，控制着整个项目的结构。在这个文件中，你需要修改的只有正文各章所在的tex文件，它们放置在`~/body/`中。

### `packages_and_settings.tex`

- 载入宏包并进行各种格式设置。简而言之，请不要轻易修改，删除本文件中的任何内容，特别是不要修改宏包的加载顺序，除非你真的知道你在做什么。这真的非常重要！！！！！！！

### `~\preface\paper_info.tex`

- 定义了各种论文的基本信息，如作者名称，完成日期，中英文关键词等，需要你自己填写修改。


### `~\preface\inner-cover.tex`

- 论文的封面设置，请勿进行任何修改，除非你真的知道你在做什么。

### `~\preface\abstract-CHS.tex, ~\preface\abstract-ENG.tex`

- 中英文的摘要（事实上还有关键词，只是关键词已经在`paper_info.tex`中填写所以在这个文件中会自动调用，你就不用管了）。


### `~\body\ch1-XXX.tex` ... ... 

- 正文各章内容。这里我们按照章进行文件分割并在`main.tex`中统一input以便管理。

### `~\body\thanks.tex`

- 致谢的内容，请自行修改填写。

### `~\body\Appendix.tex`

- 附件，可以添加多个附件。

### `~\figures\ECNU-cover.pdf`

- 封面图，请勿修改或删除。

#### `~\figures\figure_example1.png`

- 文中使用的样例图片

### `~\reference\refs.bib`

存放了所有的参考文献。虽然本模板使用的biblatex系统可以处理多bib文件，但我们依然建议你把所有条目都放在这个文件中。


### 使用方法与编译环境

- 我们强烈推荐使用TeXstudio进行论文编写。

- 本模板在Mactex下开发，理论上支持texlive 2019。不建议使用CTex套装。

- 本模板使用了biblatex来进行文献管理，且使用了biber作为后端。如果需要完整编译一次，你需要依次进行以下操作：

```
xelatex main.tex
biber main.bcf
xelatex main.tex
xelatex main.tex
```

- 是的没错，xelatex指令一共要执行三次。最后的产物就是`main.pdf`。

### 打印模式（新！）

- 由于最后打印纸质版论文需要调整单面/双面等事项，比较麻烦，所以本模板提供了一个非常易用的开关来控制是否需要启动打印模式。

- 具体地说，在`main.tex`的第五行有一条命令`\def \PrintMode{} `，默认情况下是打开的，此时产生的pdf文件里会有一些空页，且奇数页与偶数页的layout是相反的，这样在打印时只要在打印机上选择双面打印即可获得满足纸质版要求的论文，不用再做其他调整，非常方便。

- 当然在使用电子版论文时，这样的空页与layout的调整是没有必要的。此时我们只要将这行命令注释以后重新编译即可。



### 维护者：

* 汤银才（Yincai Tang）
* github: tangyc8866
