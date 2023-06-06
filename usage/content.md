# 创建内容

## 初始化 gitbook 项目

命令
```
gitbook init
```

初始化项目，按照 gitbook 规范会自动创建 `README.md` 和 `SUMMARY.md` 两个文件，具体用途见下文.

其实 `SUMMARY.md` 是电子书的章节目录，gitbook 会初始化相应的文件目录结构，所以主要是用于开发初始阶段.

## 构建 gitbook 静态网页

命令
```
gitbook build
```

构建静态网页而不启动本地服务器，默认生成文件存放在 `_book/` 目录.

输出静态网页后可打包上传到服务器，也可以上传到 github 等网站进行托管，因而主要用于发布准备阶段.

## 启动 gitbook 项目

命令
```
gitbook serve
```
启动本地服务，程序无报错则可以在浏览器预览电子书效果: http://localhost:4000

由于能够实时预览电子书效果，并且大多数开发环境搭建在本地而不是远程服务器中，所以主要用于开发调试阶段.

## 导出PDF

命令
```
gitbook pdf
```

### pdf导出过程中的问题及解决

参见[这里](https://www.jianshu.com/p/617a467bfe40)

需要单独设置的文件，打开`/.gitbook/versions/3.2.3/lib/output/ebook/getConvertOptions.js`进行以下代码的修改。
{% diff method="diffTrimmedLines" %}
```
'--chapter':                    'descendant-or-self::*[contains(concat(\' \', normalize-space(@class), \' \'), \' book-chapter \')]',
'--level1-toc':                 'descendant-or-self::*[contains(concat(\' \', normalize-space(@class), \' \'), \' book-chapter-1 \')]',
'--level2-toc':                 'descendant-or-self::*[contains(concat(\' \', normalize-space(@class), \' \'), \' book-chapter-2 \')]',
'--level3-toc':                 'descendant-or-self::*[contains(concat(\' \', normalize-space(@class), \' \'), \' book-chapter-3 \')]',
'--max-levels':                 '1',
```
```
// '--chapter':                    'descendant-or-self::*[contains(concat(\' \', normalize-space(@class), \' \'), \' book-chapter \')]',
// '--level1-toc':                 'descendant-or-self::*[contains(concat(\' \', normalize-space(@class), \' \'), \' book-chapter-1 \')]',
// '--level2-toc':                 'descendant-or-self::*[contains(concat(\' \', normalize-space(@class), \' \'), \' book-chapter-2 \')]',
// '--level3-toc':                 'descendant-or-self::*[contains(concat(\' \', normalize-space(@class), \' \'), \' book-chapter-3 \')]',
'--max-toc-links':              '0',
'--max-levels':                 '1',
```
{% enddiff %}

