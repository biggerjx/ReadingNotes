
# 本地安装gitbook


### 一、环境准备

使用gitbook必须安装node.js与GitBook，安装方法网上搜一下有很多，就不详细说明了。

1、本地安装node.js

    使用 brew 命令来安装：
    $ brew install node  

2、本地安装GitBook

    $ npm install gitbook -g  //命令行安装gitbook；
    $ npm install -g gitbook-cli  // 安装gitbook的命令行工具；
    $ gitbook -V  //用于测试gitbook是否安装成功
    
    $ npm uninstall -g gitbook //卸载gitbook
    
### 二、GitBook的常用命令

1、本地预览

    $ gitbook serve ./书名
    
2、输出一个静态网站

    $ gitbook build 本地gitbook文档地址 生成静态HTML文件的地址
    
    //下载成功后，会生成一个index.html文件可供访问。系统文件根目录下生成了一个_book的文件夹，打开就是该书籍的HTML格式了。
    
    
下载操作如下：

    yanjxMacBook-Pro:~ yanjx$ gitbook build /Users/yanjx/Documents/xqy/daydayup/ReadingNotes /Users/yanjx/Downloads
    info: 7 plugins are installed 
    info: 6 explicitly listed 
    info: loading plugin "highlight"... OK 
    info: loading plugin "search"... OK 
    info: loading plugin "lunr"... OK 
    info: loading plugin "sharing"... OK 
    info: loading plugin "fontsettings"... OK 
    info: loading plugin "theme-default"... OK 
    info: found 3 pages 
    info: found 6 asset files 
    info: >> generation finished with success in 0.7s !     
    
3、输出一个pdf

首先需要使用npm安装gitbook pdf

    $ npm install gitbook-pdf -g
    
提示ebook-convert is not installed.

（玩过kindle的都知道，calibre是一款非常方便的开源电子书转换软件。在这里，我们也是用到ebook-convert这个插件。） 

    到https://bookfere.com/tools#calibre下载一个包安装一下 
    
1）安装ebook-convert和calibre组件

    sudo npm install ebook-convert -g
    sudo npm install calibre -g

2）安装成功后，使用npm calibre -v和npm ebook-convert -v 确认版本成功安装

3）.进入https://calibre-ebook.com/download 下载mac版calibre 

直接使用npm安装的calibre好像还不够，我也不太清楚独立安装的和npm安装的到底是谁起作用了，反正3、4步我都干了 
下载安装完成后，把安装文件夹里的calibre拖拽进入应用程序 
默认安装的calibre会进入设备里，而不会进入程序，这一步很重要

4）添加ebook-convert仅path

    sudo ln -s /Applications/calibre.app/Contents/MacOS/ebook-convert /usr/local/bin

5）如果提示file exist,请执行sudo rm /usr/local/bin/ebook-convert后再执行上述命令 
请一定要删了重新放，已经存在的命令可能是旧的，或者是上述的步骤可能存在一些潜在的重复性操作输出了一个旧版的ebook-convert，这个问题将导致

    InstallRequiredError: "ebook-convert" is not installed.
    Install it from Calibre: https://calibre-ebook.com

生成pdf如下：

    yanjxMacBook-Pro:~ yanjx$ gitbook pdf /Users/yanjx/Documents/xqy/daydayup/ReadingNotes
    info: 7 plugins are installed 
    info: 6 explicitly listed 
    info: loading plugin "highlight"... OK 
    info: loading plugin "search"... OK 
    info: loading plugin "lunr"... OK 
    info: loading plugin "sharing"... OK 
    info: loading plugin "fontsettings"... OK 
    info: loading plugin "theme-default"... OK 
    info: found 4 pages 
    info: found 6 asset files 
    info: >> generation finished with success in 7.5s ! 
    info: >> 1 file(s) generated 

遇到的问题：

直接在根路径下执行gitbook pdf 命令时不能在/Users/yanjx/Documents/xqy/daydayup/ReadingNotes文件夹中生成pdf文件，需要在/Users/yanjx/Documents/xqy/daydayup/ReadingNotes文件夹中执行gitbook pdf命令才能生成pdf文件。

    
4、查看帮助

    $ gitbook -h


### 三、集成至GitHub

1、在有GitHub账号的前提下，新建一个project

2、Clone with HTTPS

3、编辑自己的gitbook

4、提交代码，同步至github即可



