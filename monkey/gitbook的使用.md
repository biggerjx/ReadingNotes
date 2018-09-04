参考 https://blog.csdn.net/stu059074244/article/details/77767835，感谢作者分享


# gitbook命令

### 1、gitbook的8个命令

    build [book] [output]       build a book
        --log                   Minimum log level to display (Default is info; Values are debug, info, warn, error, disabled)
        --format                Format to build to (Default is website; Values are website, json, ebook)
        --[no-]timing           Print timing debug information (Default is false)

    serve [book] [output]       serve the book as a website for testing
        --port                  Port for server to listen on (Default is 4000)
        --lrport                Port for livereload server to listen on (Default is 35729)
        --[no-]watch            Enable file watcher and live reloading (Default is true)
        --[no-]live             Enable live reloading (Default is true)
        --[no-]open             Enable opening book in browser (Default is false)
        --browser               Specify browser for opening book (Default is )
        --log                   Minimum log level to display (Default is info; Values are debug, info, warn, error, disabled)
        --format                Format to build to (Default is website; Values are website, json, ebook)

    install [book]              install all plugins dependencies
        --log                   Minimum log level to display (Default is info; Values are debug, info, warn, error, disabled)

    parse [book]                parse and print debug information about a book
        --log                   Minimum log level to display (Default is info; Values are debug, info, warn, error, disabled)

    init [book]                 setup and create files for chapters
        --log                   Minimum log level to display (Default is info; Values are debug, info, warn, error, disabled)

    pdf [book] [output]         build a book into an ebook file
        --log                   Minimum log level to display (Default is info; Values are debug, info, warn, error, disabled)

    epub [book] [output]        build a book into an ebook file
        --log                   Minimum log level to display (Default is info; Values are debug, info, warn, error, disabled)

### 2、命令使用示例

初始化

    $ gitbook init

构建:在_book 目录生成一个静态站点的资源 

    $ gitbook build

获取更多错误消息

    $ gitbook build ./ --log=debug --debug

启动服务

    $ gitbook serve

列出 gitbook 所有的命令

    $ gitbook help 
    
输出 gitbook-cli 的帮助信息

    $ gitbook --help

列出本地所有的gitbook版本
    
    $ gitbook ls
    
指定log的级别

    $ gitbook build --log=debug
    
输出错误信息

    $ gitbook builid --debug


# gitbook 常用知识

### 1、目录文件含义

 - README.md
 
    封面 
 
 - SUMMARY.md 
 
    目录

 - Glossary.md
 
    电子书内容中需要解释的词汇可在此文件中定义。词汇表会被放在电子书末尾。


 - book.json
 
    电子书的配置文件
    
 - 电子书封面
 
   封面图片命名为 cover.jpg，放到电子书项目。
   
   
### 2、忽略文件和文件夹
  GitBook将读取 .gitignore，.bookignore 和 .ignore 文件。
  
  
### 3、做好看的目录

锚点：目录中的章节可以使用锚点指向文件的特定部分。


    * [文章1](part1/README.md#writing
   
 部分
 
    为以标题或水平线 ---- 分隔的部分  
    
    
    ### Part 1
    
    ----
    
    ### Part 2



    

    

