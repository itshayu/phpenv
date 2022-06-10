## VSCODE XDEBUG
```
{
    "name": "Listen for Xdebug",
    "type": "php",
    "request": "launch",
    "port": 9003,
    "xdebugSettings": {
        "max_data": 9999,
        "max_children": 9999
    },
    "pathMappings": {
        "/data/web_data/web/app/": "${workspaceFolder}"
    }
}
```

---
## xhprof 乱码问题
https://gitlab.alpinelinux.org/alpine/aports/-/issues/11144

##### dot 脚本
```
echo "graph { a -- b }" > /tmp/bad/bad.dot
# 指定字体
dot -Nfontname='NotoSansMro Regular' -Tpng  ./bad.dot -o ./bad.png
```

