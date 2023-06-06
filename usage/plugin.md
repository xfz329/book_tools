# 使用插件

## 默认插件

Gitbook默认带有7个插件（功能性5个，搜索有两个，主题一个）：

* livereload 热加载插件
* highlight 语法高亮插件
* search 搜索插件
* lunr 搜索插件后台服务
* sharing 分享插件
* fontsettings 字体设置插件
* theme-default 主题

但这些插件功能受限，我们可以自己安装更多插件，实现更多的功能。

## 本文档涉及的插件

{% includeCsv src="../csv/plugins.csv", useHeader="true" %}

{% endincludeCsv %}

## 更多插件

参见[这里](https://www.mapull.com/gitbook/comscore/custom/plugin/other/)

参见[这里](https://blog.csdn.net/TOMOCAT/article/details/120399651)

参见[官方仓库](https://www.npmjs.com/search?q=gitbook)

## 一些插件的用法示例

### page-treeview

默认page-treeview会带有版权信息。

![1](../images/page-tree-view.jpg)


如果不想要，需要在插件目录中打开：`/node_modules/gitbook-plugin-page-treeview/lib/index.js`。
将97行改成
```
  return renderContent;
```

### diff

类似git的代码比较，有多种比较方式，参见[这里](https://snowdreams1006.github.io/gitbook-plugin-diff/zh/)

{% diff %}
```bash
beep boop
the cat is palying with cap
what
```
```bash
beep boob blah
the cat is palying with cat
who
```
{% enddiff %}

### include-csv

从csv文件中导入数据，需要注意，该插件对依赖`csv-parse`的版本有要求，需要安装4.9.1版本，安装代码
```
npm i csv-parse@4.9.1
```

使用范例，参见[此处](https://www.mapull.com/gitbook/comscore/custom/plugin/other/csv.html)

{% includeCsv src="../csv/123.csv", useHeader="true", limit=5 %}

{% endincludeCsv %}

### chart

使用范例，参见[此处](https://www.mapull.com/gitbook/comscore/custom/plugin/other/chart.html)
{% chart %}
{
    "data": {
        "type": "bar",
        "columns": [
            ["data1", 30, 200, 100, 400, 150, 250],
            ["data2", 50, 20, 10, 40, 15, 25]
        ],
        "axes": {
            "data2": "y2"
        }
    },
    "axis": {
        "y2": {
            "show": true
        }
    }
}
{% endchart %}