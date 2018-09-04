





脚本

    #!/bin/bash
    
    gitbook install
    gitbook build
    cd _book
    rm -fr /opt/gitbook/book
    mkdir /opt/gitbook/book
    mv ./* /opt/gitbook/book