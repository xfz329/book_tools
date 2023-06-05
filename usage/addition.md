# 补充

## 插入图片

插入图片的标准markdown语法是
```markdown
![name](url)
![name](path)
```
其中，前者是网络图片，后者是相对路径，可以引用本地图片。

若工程需导出成pdf，选择前者可能会出现图片链接超时（特别是图片需要翻墙，如自建图床）。因此，更推荐用后者的形式。

具体而言，在工程路径下新建`images`文件夹，然后安装相对路径关系引用图片。
```
![nvm](../images/nvm.jpg)
```

## 插入公式

公式默认是latex语法，但实际上很简单。

段内公式$$x=-\frac{b}{2a} \pm \frac{\sqrt{b^2-4ac}}{2a}$$

```
段内公式$$x=-\frac{b}{2a} \pm \frac{\sqrt{b^2-4ac}}{2a}$$
```

段间公式
$$
\delta_F(f,g)=\inf \max \limits_{\alpha,\beta \; t \in (0,1)} d(f(\alpha(t)), g(\beta(t)))
$$

```
段间公式
$$
\delta_F(f,g)=\inf \max \limits_{\alpha,\beta \; t \in (0,1)} d(f(\alpha(t)), g(\beta(t)))
$$
```

### 退而求其次

编辑好截图吧。
