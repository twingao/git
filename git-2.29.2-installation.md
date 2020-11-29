# Git 2.29.2 安装

Git的下载页面[https://mirrors.edge.kernel.org/pub/software/scm/git/](https://mirrors.edge.kernel.org/pub/software/scm/git/)，下载地址[https://mirrors.edge.kernel.org/pub/software/scm/git/git-2.29.2.tar.gz](https://mirrors.edge.kernel.org/pub/software/scm/git/git-2.29.2.tar.gz)

先安装依赖。

    yum install -y curl-devel expat-devel gettext-devel openssl-devel zlib-devel gcc perl-ExtUtils-MakeMaker

由于git 1.8.3.1会被作为依赖安装，卸载git 1.8.3.1版本。

    yum remove git

解压git文件。

    tar xzvf git-2.29.2.tar.gz
    cd git-2.29.2

编译和安装git。

    make prefix=/usr/local/git all
    make prefix=/usr/local/git install

配置环境变量。

    vi /etc/profile
    export PATH=$PATH:/usr/local/git/bin

    source /etc/profile

查看git版本。

    git --version
    git version 2.29.2

删除安装包文件。

    rm -rf git-2.29.2
    rm git-2.29.2.tar.gz
