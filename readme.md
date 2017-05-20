<!-- START doctoc generated TOC please keep comment here to allow auto update -->
<!-- DON'T EDIT THIS SECTION, INSTEAD RE-RUN doctoc TO UPDATE -->

<!-- END doctoc generated TOC please keep comment here to allow auto update -->

# 哈　尔　滨　医　科　大　学  
# 硕博士学位论文xelatex模版
## 最后更新时间 2017-05-20
### 使用方法

最简使用方式如下

>		1. 下载安装vmware player
>		http://www.vmware.com/products/player/playerpro-evaluation.html
>		2. 下载已测试的虚拟机
>		http://pan.baidu.com/s/1i5Df9nJ
>		3. 在VM player中，导入虚拟机。用户名ubuntu密码123123
>		4. 在虚拟机中使用模板，直接双击其中的main.tex进行修改
>		5. 修改标题，作者等信息，观察代码，修改原有章，尝试三线表，尝试引用。
>		引用文献管理软件：很多，如endnote mendeley等。生成对应的bib文件后，在tex中用\citeup等方式引用。
>		6. 正式写作。tex最好的一点就是引文、表格、图片的排版基本不需要干预。

### 更新记录
2017-05-20

修订格式

现存问题：

1、部分格式要求需输出后，在PDF中手动删除目录下方罗马页码

2、如对单双页需使用不同页眉，自行设置

3、参考文献引用格式会添加.bib文件中的网址，本人不会修改设置参考文献格式.bst文件。Mendeley从Pubmed上抓下来的文献都是有网址的，需手动删除。别的引文管理软件未测试。

推荐插入引文标准方法：
>		1.Mendeley直接从pubmed上抓取，抓取时可建立相应文件夹。（需翻墙，也可能是我的网络不好。pubmed对部分vps提供商的部分地址段有封锁（提示滥用），按需选择。）
>		2.Mendeley内，手动插入参考文献的tag（标签），并选择需要的文献输出bib文件
>		3.在文本编辑器中（windows建议用noteapd++），修改这个中间bib文件，将mendeley-tags = {自定义标签}的标签，复制到此文献的@article{标签, （位于第一行）处。
>		4.复制此中间bib中的内容到，MyCollection.bib（真正使用的bib文件）中，

4、部分官方指定查重网站对pdf格式不提供支持，需手动复制。复制到word中可能出现□。参考文献几个字如果时□□□□，则必须修改为“参考文献”，否则可能将参考文献一并查重，造成重复率过高。

5、linux中，图片文件名可以使用中文，可用png，已测试。
   各种引用标签我自己使用的英文，功能正常；中文未测试。

2016-11-21

添加了缩略词表


### 查重说明

部分查重网站支持pdf，部分官方指定网站不支持pdf。需手动复制到word中，可能出现□。参考文献几个字如果时□□□□，则必须修改为“参考文献”，否则可能将参考文献一并查重，造成重复率过高。

### 其他使用说明

1. 本模板现在基本可用。

2. 参考文献排版很方便（有多方便不方便说）。

3. 在虚拟机中打开main.tex，改改改之后，点击绿色双箭头构建并查看（F5）即可。生成引用及目录需要点2次。

4. 新建章节可按图索骥，用\include{body/新的tex}建立章节。



### 如何帮助完善此模板

1. 需修改的地方可fork后，你的github上就出现了同名的项目，这个项目就属于你自己了，你把这个自己的项目git clone到本地，修修改改，然后push到你自己的项目里，在github上你的项目页面点Pull request。提交至此版本即可。

2. 此模板非官方模板，参照word模版制作。如果需要奇偶页眉不同，自行查找调整。

3. 标题若长于一行。直接在setup/format %内封 后修改

4. 可直接插入png等格式图片。

5. 中英双语切换开关为硕士中文，博士中英文。

### 关于字体

强制伪加粗宋体，其余自体遵循标准。




### 关于编译

#### 那些莫名其妙的编译提示错误……

参考google

#### 那种完美的中文引用样式……

建议使用\citeup{引用词}

### 对于使用者


1. 推荐使用上文的虚拟机

2. 文件列表

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
