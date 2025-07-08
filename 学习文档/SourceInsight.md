# SourceInsight相关技术点

## 一、基础概念

SourceInsight 是一款功能强大的源代码编辑器和分析工具，主要用于帮助开发人员高效阅读、编写和理解复杂的代码项目，适合处理大型代码库，支持多种编程语言，包括 C、C++、Java、Python 等，核心优势在于其出色的代码导航和分析能力。它通过动态解析源代码生成符号数据库，提供快速跳转、函数调用关系图、上下文引用高亮等功能，使开发者能轻松追踪变量、函数和类的定义与引用。此外，其强大的语法高亮、自动补全和代码片段功能进一步提升了编码效率。

## 二、基本操作

- **工程新建/添加**

1. 点击菜单[Project]>[New Project]；

2. 在弹出的【New Project】对话框中设置【New project name】（项目的名称）；

3. 设置【Where do you want to store the project data file?】 （项目文件保存位置）（也就是想把Source Insight项目放在哪里？）；

4. 点击【Browse】按钮选择源码的目录；
5. 在新弹出的对话框中，点击【Add】或【Add All】（“Add”是手动选择需要添加的文件，而“Add All”是添加所有文件）（同样的“Remove File”，“Remove All”是移除单个文件或者移除所有文件），一般使用“Add All”；
6. 在弹出的提示框中勾上【Recursively add lower sub-directories】(递归添加下级的子目录)并点击【OK】（另外一个【Include top level…】已经是默认被勾上的，不用管）；
7. 勾上【Show only known file types】（已经是默认被勾上的，不用管）；
8. 添加文件完成后点击【Close】，此时界面会返回到主界面；

- **文件新建/添加**
- **符号表同步**

同步文件的意思是让**8Source Insight去解析源码，生成数据库**，这样有助于以后阅读源码。比如点击某个函数时就可以飞快地跳到它定义的地方。

1. 先点击菜单【**Project**】>【**Synchronize Files**】；
2. 在弹出的对话框中 勾上【**Force all files to be re-parsed**】（强制解析所有文件）；
3. 点击【**Start**】按钮开始同步；

* **修改编码格式**

  * 更改所有文件编码格式

    1. 菜单栏中 **【Options】** > **【Preferences**】 >**File**标签中，最下面的“**Default encod­ing**” 选项；

    2. 选择“**Chinese Simplified（GB2312）CP:936**”（简体中文）这个编码即可改为[GB2312](https://so.csdn.net/so/search?q=GB2312&spm=1001.2101.3001.7020)；

  * 更改单个文件编码

    1. 菜单栏中 **【File】** > **【Reload As Encoding…】** > **【Chinese Simplified（GB2312）CP:936】** > 选择后，点击**load**；

- **视图切换**:切换成普通视图：View - Mono Font View 快捷键`Alt + F12` 
- **常用窗口打开/关闭**
  - 1. **Project Window**窗口：查看我们的工程所在文件夹以及文件夹下的文件。
       * ![](./SourceInsight.assets/project%E7%AA%97%E5%8F%A3.png)
    2. **Symbol Window**窗口：用于查看我们开启的文件以及文件内所包含的函数。
       * ![](./SourceInsight.assets/symbol%E7%AA%97%E5%8F%A3.png)
    3. **Context Window**窗口：用于查看，函数中某个参数与函数的关系。
       * ![](./SourceInsight.assets/contxt%E7%AA%97%E5%8F%A3.png)
    4. **Relation Window**窗口：用于查看函数以及参数所定义的位置。
       * ![](./SourceInsight.assets/relation%E7%AA%97%E5%8F%A3.png)
- **搜索引用**
  - 常用的一种查找方式是选择**Search/Lookup References**，在弹出的Loopup References窗口进行查找操作。在SearchMethod中有四种可选的查找方式：Simple String、Regular Expression、 KeywordExpression和Look Up Reference。其中SimpleString是最普通的查找方式，可以查找文件中出现的任意字符或字符，甚至可以查找 _upap || u这样的字符串，但是在工程较大时，查找过程会较慢。
  - **SearchFiles**，在**File Name框**中可以填入文件名或文件夹。注意当要查询的文件夹双包含子文件夹时，可以勾选Options中的IncludeSubdirectiories，实现对各层文件的递归搜索。
  - **SearchProject**，操作与LoopupReferences几乎完全一致，它们各自保存上次搜索的配置。
