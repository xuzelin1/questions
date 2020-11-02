
## attribute

HTML 中的元素拥有属性—— attribute，这些属性可以配置元素，或者调整元素的行为表现，进而满足用户的需要。

以下是一些通用的属性，他们可以应用于任何元素上

|属性名称|属性描述|
|-|-|
|accesskey	|规定激活元素的快捷键。
|class	|规定元素的一个或多个类名（引用样式表中的类）。
|contenteditable|	规定元素内容是否可编辑。
|contextmenu|	规定元素的上下文菜单。上下文菜单在用户点击元素时显示。
|data-*|	用于存储页面或应用程序的私有定制数据。
|dir|	规定元素中内容的文本方向。
|draggable|	规定元素是否可拖动。
|dropzone|	规定在拖动被拖动数据时是否进行复制、移动或链接。
|hidden	|规定元素仍未或不再相关。
|id	|规定元素的唯一 id。
|lang|	规定元素内容的语言。
|spellcheck|	规定是否对元素进行拼写和语法检查。
|style|	规定元素的行内 CSS 样式。
|tabindex|	规定元素的 tab 键次序。
|title	|规定有关元素的额外信息。
|translate|	规定是否应该翻译元素内容。

> 以上属性虽然可以应用于所有元素，但是不一定支持所有浏览器，或者说某些浏览器对其支持性不完善（translate 属性所有的浏览器支持性都不是很好）。

除了以上的元素属性，一些元素有可选的属性支持。像 `img` 标签，可选属性有 height、width 等。

我们可以通过 `setAttribute()`、`remveAttribute()` 和 `getAttribute()` 来操作元素的属性。

## data-*

在上面的通用属性表格中，其中有一个是 `data-*`，是 HTML5 中新增的，可以查看这个
[data-attribute规范](https://html.spec.whatwg.org/multipage/dom.html#custom-data-attribute)

定义：
`data-*` 是HTML5的一个新全局属性，是一个被称为**自定义数据属性**的属性。自定义数据属性旨在存储页面或应用程序专用的自定义数据，对于这些自定义数据没有更多合适的属性或元素。`data-*` 赋予我们在所有 HTML 元素上嵌入自定义数据属性的能力，并可以通过脚本在 HTML 与 DOM 表现之间进行专有数据的交换。

自定义属性旨在供站点自己的脚本使用，而不是可公开使用的元数据的通用扩展机制。因为这些自定义属性其他站点并不一定适用。

## element.dataset

`HTMLElement.dataset` 属性允许在读取模式和写入模式下访问在 HTML或 DOM中的元素上设置的所有自定义数据属性(data-*)集，该集合是 `DOMStringMap`，每个自定义属性的条目映射。

dataset 属性可以被读取和写入，但是写入必须是它的属性，比方说下面这个例子：

```

```


DOMStringMap

## CSS 与 Attribute

CSS 中，可以使用 `attr()` 来处理元素中的属性，比如下面这个例子就可以实现悬浮展示一些提示信息，通过attr

```html
<div content="前端学习相关知识——属性">前端学习...</div>
```

```css
  div {
    margin: auto;
    margin-top: 100px;
    position: relative;
    line-height: 16px;
    box-sizing: content-box;
  }
  div:hover::after {
    content: attr(content);
    position: absolute;
    top: -100%;
    background-color: #efefef;
    padding: 3px 5px;
  }
```

使用 attr 的话相对可以实现的功能较有限，当使用 data-* 时，我们可以利用 HTML 的属性做得更多。我们可以通过这个特殊的属性来做选择器。

## 参考文章

[HTML5中的 data-* 如何处理数据详解](https://github.com/lvzhenbang/article/blob/master/js/data-attribute.md)