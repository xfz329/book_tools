# 配置插件
打开工程目录下的`book.json`文件，将其中内容替换为以下内容。
```json
{
    "title": "My Book",
    "author": "Author",
    "pdf": {
        "margin": {
            "left": 0,
            "right": 0,
            "top": 0,
            "bottom": 0
        },
        "fontSize": 15
    },      
    "plugins": [
        "-lunr",
        "-sharing",
        "-search",
        "-highlight",
        "search-pro",
        "back-to-top-button", 
        "code",
        "copy-code-button",
        "theme-comscore",
        "splitter",
        "hide-element",
        "page-treeview",
        "popup",
        "expandable-chapters",
        "chapter-fold",
        "katex",
        "prism",
        "insert-logo",
        "diff",
        "include-csv",
        "chart"
    ],
    "pluginsConfig": {
        "code": {
            "copyButtons": false
        },
        "hide-element": {
            "elements": [".gitbook-link"]
        },
        "page-treeview": {
			"copyright": "Copyright &#169; BME207",
			"minHeaderCount": "2",
			"minHeaderDeep": "2"
		},
        "insert-logo": {
            "url": "https://pic1.zhimg.com/v2-480076570d707295d81bdde6e5f4591e_1440w.jpg?source=172ae18b",
            "style": "background: none; max-height: 100px; min-height: 60px"
        },
        "diff": {
            "method": "diffTrimmedLines",
            "options": {
                "newlineIsToken": true
            }
        }
    }
}
```
其中，`title`与`author`后面的字符串数值可以根据需求替换成实际书名与作者名。重新`gitbook build`与`gitbook serve`。

