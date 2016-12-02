<!-- START doctoc generated TOC please keep comment here to allow auto update -->
<!-- DON'T EDIT THIS SECTION, INSTEAD RE-RUN doctoc TO UPDATE -->

- [哈　尔　滨　医　科　大　学](#哈　尔　滨　医　科　大　学)
- [硕博士学位论文XeLaTeX模版](#硕博士学位论文xelatex模版)

<!-- END doctoc generated TOC please keep comment here to allow auto update -->

#哈　尔　滨　医　科　大　学  
#硕博士学位论文xelatex模版

### 使用方法
1. 已经配置好的虚拟机文件如下
>        http://pan.baidu.com/s/1i5Df9nJ
>        ubuntu的密码123123
>        需安装vmware player
>        http://www.vmware.com/products/player/playerpro-evaluation.html
	ddd引用文献管理软件：很多，如endnote mendeley等。生成对应的bib文件后，在tex中用\citeup等方式引用。
2. 本模板只是初步可用的xeLaTeX版，需要有精力的同学进一步完善。

3. 参考文献排版是最令人心动的功能。
4. 在虚拟机中打开main.tex，改改改之后，点击绿色双箭头构建并查看（F5）即可。生成引用及目录需要点2次。

5. 用xeLaTeX，中文支持优秀。生成的pdf可查重

6. 新建章节可按图索骥，用\include{body/新的tex}建立章节。

7. 需修改的地方可fork后，你的github上就出现了同名的项目，这个项目就属于你自己了，你把这个自己的项目git clone到本地，修修改改，然后push到你自己的项目里，在github上你的项目页面点Pull request。提交至此版本即可。

8. 此模板非官方模板，参照word模版制作，强制伪加粗宋体。

9. 标题若长于一行，不要用“引用”的方式修改。直接在setup/format %内封 后修改

10. 可直接插入png等格式图片。

11. 中英双语切换开关为硕士中文，博士中英文。
### 关于字体

XeLaTeX的字体缺省为winfonts，定义在如下文件（Linux）:

	/usr/share/texlive/texmf-dist/tex/latex/ctex/fontset/ctex-xecjk-winfonts.def

模板中就是手动载入的字体。
怕麻烦的同学，这里提供已配置好的linux虚拟机文件。使用
### 关于查重

拥有完美的可复制支持。可以使用pdf查重。
> 这意味着什么？  
> 这意味着word死忠可以哭晕在厕所了……

使用版本管理毕业论文的同学，可以优雅地欣赏如下两个场景了：

word文件夹模式一：

		毕业论文第1章.doc 
		毕业论文第2章.doc 
		毕业论文第3章.doc 
		毕业论文第4章.doc 
		毕业论文第5章.doc 
		毕业论文完整版.doc 
		毕业论文完整版改.doc 
		毕业论文完整版再改.doc 
		毕业论文完整版再再改.doc 
		毕业论文完整版再也不改.doc 
		毕业论文完整版再也不再改.doc 
		毕业论文完整版死都不改.doc 
		毕业论文完整版不死还得改.doc 
		……

word文件夹模式二：

		毕业论文第1章.doc 
		毕业论文第2章.doc 
		毕业论文第3章.doc 
		毕业论文第4章.doc 
		毕业论文第5章.doc 
		毕业论文完整版20150701.doc 
		毕业论文完整版20150702.doc 
		毕业论文完整版20150703.doc 
		毕业论文完整版20150704.doc 
		毕业论文完整版20150705.doc 
		……


### 关于编译

#### 那些莫名其妙的编译提示错误……

有些HIT刀客（Doctor）行走江湖过惯了快意恩仇的生活，眼里不揉沙子。
把模板一点不动地在本地运行一下，发现了提示错误，于是有的刀客转身奔向敌营Word，有的刀客发冲冠一怒开山立派，自立门户。

其实这不是错误……

因为LaTeX最初设计用来排版英文，所以对于中文在基因上先天不足，唯有靠后天补营养。
当bibTeX使用模板中的参考文献样式bst文件来排版参考文献时，会弹出错误提示，这个错误提示不是真正意义的错误。
为什么呢？因为我们的目的已经达到了，已经生成好了bbl文件。
于是这个尴尬的局面出现了：如果采用如下方法在Makefile文件里面将bibTeX错误提示屏蔽掉，

	bibtex main || true

那么这也会屏蔽bib文件中真正的格式错误。
所以到底屏不屏蔽，还是留给各位刀客自己决定吧。

#### 那种完美的中文引用样式……

要么上标，要么下标，综述是不是枯燥又无聊！
所以一定有一种[中文引用样式](http://yanshuo.name/cn/2015/06/latex/)会使综述的时间逻辑（年份）和空间逻辑（该文献在文章最后哪一个部分）都很清晰，且含有主语（作者名）。
用这样的引用样式写出的文献综述是不是很文学范？

使用方法：正文中的引用方式是`\citeayu`；
编译方法是：

	make -f MakefileAYU

## 这个网站的使用说明

### 对于开发者

当前master分支为临时可用的XeLaTeX模板。
### 对于使用者
1. 推荐使用texlive安装包，完成安装后需手动更新至最新版。

2. 稳定版本的发布地址（可在此下载稳定的版本）

3. 该模板目录结构和各自文件大致功能

		├── appendix （论文后面的附表，这里需要编写）
		├── body （论文的正文部分，正文写在这里需要编写）
		├── clean.bat （用于清理编译过程中的中间文件，使目录干净点）
		├── cover.tex （这是论文中封面，摘要部分，这里需要编写）
		├── figures （存放论文的图片的文件夹）
		├── GBT7714-2005NLang-HIT.bst （参考文献样式文件）
		├── main.pdf （最终生成的论文）
		├── main.tex （论文的主文件，有需要的时候要适当修改调整这个文件）
		├── Makefile （自动编译文件，这个文件里面定义了编译方式）
		├── MakefileAYU （自动编译文件，这个文件里面定义了编译方式）
		├── readme.md
		├── reference.bib （用于存放参考文献，BibTeX格式，需要编写）
		├── setup （论文的设置部分）
		├── tex.snippets （是snippet 模板，用来给vim编辑器用）
		├── XeLaTeX支持说明(第１章开始).pdf
		└── 模板更新记录.txt
