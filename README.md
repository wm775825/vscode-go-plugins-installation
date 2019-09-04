# Go语言vscode插件安装

由于GFW的存在，vscode自动安装插件可能会失败，以下为手动安装指令。

```shell
    export GOPATH=~/go
    # 打开MODULE功能，用以支持代理。
    export GO111MODULE=on
    # 使用代理地址
    export GOPROXY=https://goproxy.io
    # 装dlv时加上-u发现只能生成pkg不能生成bin
    go get -v github.com/go-delve/delve/cmd/dlv
    go get -u -v github.com/ramya-rao-a/go-outline
    go get -u -v github.com/acroca/go-symbols
    # 这个是gocode-mod插件，安装后需要将$GOPATH/bin/gocode改名为gocode-mod
    go get -u -v github.com/stamblerre/gocode
    mv $GOPATH/bin/gocode $GOPATH/bin/gocode-mod
    # 下面这个gocode要在上边gocode之后装
    go get -u -v github.com/nsf/gocode
    go get -u -v github.com/rogpeppe/godef
    go get -u -v golang.org/x/lint/golint
    go get -u -v github.com/fatih/gomodifytags
    go get -u -v github.com/uudashr/gopkgs/cmd/gopkgs
    go get -u -v golang.org/x/tools/cmd/gorename
    go get -u -v github.com/sqs/goreturns
    go get -u -v golang.org/x/tools/cmd/guru
    go get -u -v github.com/josharian/impl
    go get -u -v github.com/haya14busa/goplay/cmd/goplay
    go get -u -v github.com/davidrjenni/reftools/cmd/fillstruct
    go get -u -v github.com/godoctor/godoctor
    # [待解决]下一条运行错误，提示:malformed module path "github.com/cweill/gotests/...": double dot 
    go get -u -v github.com/cweill/gotests/...
    # 以下插件vscode不要求，可自行决定是否安装
    go get -u -v golang.org/x/tools/cmd/godoc
    go get -u -v github.com/zmb3/gogetdoc
```
