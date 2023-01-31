---
title: <textarea>：文本区元素
slug: Web/HTML/Element/textarea
---

{{HTMLSidebar}}

**HTML `<textarea>` 元素**表示一个多行纯文本编辑控件，当你希望用户输入一段相当长的、不限格式的文本，例如评论或反馈表单中的一段意见时，这很有用。

{{EmbedInteractiveExample("pages/tabbed/textarea.html", "tabbed-standard")}}

上述例子展示了 `<textarea>` 的几个特点：

- 为了提高无障碍（accessibility），用于将 `<textarea>`与一个 {{htmlelement("label")}} 关联的 `id` 属性。
- `name` 属性，用于设置随表单一同提交到服务器的相关数据的名字。
- `rows` 和 `cols` 属性，用于声明 `<textarea>` 的精确尺寸。这对于一致性非常有帮助，因为不同浏览器的默认值常常不一样。
- 位于开始标签和闭合标签之间的默认内容。`<textarea>` 不支持 `value` 属性。

`<textarea>` 还可以使用 `<input>` 中的一些常见属性，如`autocomplete`, `autofocus`, `disabled`, `placeholder`, `readonly`, 和 `required`。

## 属性

这个元素包含了[全局属性](/zh-CN/docs/HTML/Global_attributes)。

- {{htmlattrdef("autocapitalize")}} {{non-standard_inline}}
  - : iOS 的非标准属性（运行在 iOS 上的 Safari、Firefox、Chrome 都支持），文本是否自动首字母大写。在 iOS5 和之后的版本上有效。可能的值为：

    - `none`: 禁用首字母大写。
    - `sentences`: 句子的首字母大写。
    - `words`: 单词或者字母的首字母大写。
    - `characters`: 全部字母大写。
    - `on`: {{deprecated_inline()}} 自 iOS 5 废弃。
    - `off`: {{deprecated_inline()}} 自 iOS 5 废弃。
- {{htmlattrdef("autocomplete")}}
  - : 是否使用浏览器的记忆功能自动填充文本。可能的值有：

    - `off`: 不使用浏览器的记忆自动填充，使用者必须输入他们想要输入的所有内容。或者网页提供了自己的自动填充方法。
    - `on`: 浏览器根据用户之前输入的内容或者习惯，在用户输入的时候给出相应输入提示。如果不指明**autocomplete**属性，浏览器会从父级的表单元素上解析是不是开启这个属性。表单元素可以是 `textarea` 元素的父级{{HTMLElement("form")}}或者 `textarea`有跟表单相同的 id（参见下面的 form 属性）。更多请查看{{HTMLElement("form")}}的{{htmlattrxref("autocomplete", "form")}} 属性。
- {{ htmlattrdef("autofocus") }}
  - : 页面加载完毕之后是否自动给本元素添加焦点。只有跟表格关联的才能使本属性生效。
- {{ htmlattrdef("cols") }}
  - : 文本域的可视宽度。必须为正数，默认为 20 (HTML5)。
- {{ htmlattrdef("disabled") }}
  - : 禁用文本域。默认为 false。如果未指定，也可以从父级上如{{ HTMLElement("fieldset") }}继承而来。
- {{ htmlattrdef("form") }}
  - : 指定跟自身相关联的表单。值必须为本文档内的表单的 ID，如果未指定，就是跟当前所在的表单元素相关联。这就允许你在文档的任意地方放置文本域元素。
- {{ htmlattrdef("maxlength") }}
  - : 允许用户输入的最大字符长度 (Unicode) 。未指定表示无限长度。
- {{ htmlattrdef("minlength") }}
  - : 允许用户输入的最小字符长度 (Unicode)
- {{ htmlattrdef("name") }}
  - : 元素的名称。
- {{ htmlattrdef("placeholder") }}
  - : 向用户提示可以在控件中输入的内容。在渲染提示时，占位符文本中的回车符 (\r) 或换行符 (\n) 一定会被作为行断（换行）处理。

    > **备注：** Placeholders should only be used to show an example of the type of data that should be entered into a form; they are _not_ a substitute for a proper {{HTMLElement("label")}} element tied to the input. See [`<input>` labels](/zh-CN/docs/Web/HTML/Element/input#标签) for a full explanation.
- {{ htmlattrdef("readonly") }}
  - : 不允许用户修改元素内文本。和 `disabled` 属性不同的是，这个能让用户点击和选择元素内的文本。如果在表单里，这个元素的值还是会跟随表单一起提交。
- {{ htmlattrdef("required") }}
  - : 提示用户这个元素的内容必填。
- {{ htmlattrdef("rows") }}
  - : 元素的输入文本的行数（显示的高度）。
- {{ htmlattrdef("spellcheck") }}
  - : 该属性设为 true 时，表明该元素会做拼写和语法检查。属性值为 default 时，表明元素有默认行为，可能会基于父元素的 spellcheck 值。属性值为 false 时，表明元素不做拼写和语法检查。
- {{ htmlattrdef("wrap") }}
  - : 指定文本换行的方式。默认为 soft。可能的值为：

    - hard: 在文本到达元素最大宽度的时候，浏览器自动插入换行符 (CR+LF) 。比如指定 `cols`值。
    - soft: 在到达元素最大宽度的时候，不会自动插入换行符。

## 使用 CSS 样式

`<textarea>` 是 [可被替换的元素](/zh-CN/docs/CSS/Replaced_element)——其有自己的固有尺寸，像。默认情况下，其 {{cssxref("display")}} 值为 `block`。与其他表单元素相比，这个元素相对比较容易设置样式，使用常规的 CSS 就可以轻松设置它的盒模型、字体、颜色方案等。

[Styling HTML forms](/zh-CN/docs/Learn/HTML/Forms/Styling_HTML_forms) 这个页面提供了一些关于 `<textarea>` 样式的有用提示。

### 基线不一致

HTML规范没有定义 `<textarea>`的基线位置，因此不同的浏览器将其设置到不同的位置。对于Gecko， `<textarea>`基线设置在文本区域第一行的基线上，在另一个浏览器上，它可以被设置在<textarea>框的底部。请不要在上面使用{{cssxref("vertical-align")}}`: baseline`；因为它会导致不可预测的行为。

### 控制文本区是否可调整大小

在大多数的浏览器中, `<textarea>`s 的大小是可调整的 — 你会注意到右侧角落的拖动手柄, 它可以用来改变此元素在页面上的大小。 它由css属性{{ cssxref("resize") }}控制，默认情况下调整大小是启用的,  但你可以将`resize`的值调整为`none`来将它显式地禁用:

```css
textarea {
  resize: none;
}
```

### 在样式中使用有效值和无效值

Valid and invalid values of a `<textarea>` element (e.g. those within, and outside the bounds set by `minlength`, `maxlength`, or `required`) can be highlighted using the {{cssxref(":valid")}} and {{cssxref(":invalid")}} pseudo-classes. For example, to give your textarea a different border depending on whether it is valid or invalid:

```css
textarea:invalid {
  border: 2px dashed red;
}

textarea:valid {
   border: 2px solid lime;
}
```

## 示例

### HTML

```html
<textarea name="textarea" rows="10" cols="50">Write something here</textarea>
```

{{ EmbedLiveSample('HTML','600','200') }}

### 基本示例

下面的示例显示了一个设置了行和列数和一些默认内容的非常简单的文本区域。

```html
<textarea name="textarea"
   rows="10" cols="50">Write something here</textarea>
```

{{ EmbedLiveSample('基本示例','600','150') }}

### 最小和最大长度

此示例的最小字符数和最大字符数分别为10和20。试试看。

```html
<textarea name="textarea"
   rows="5" cols="30"
   minlength="10" maxlength="20">Write something here</textarea>
```

{{ EmbedLiveSample('最小和最大长度','600','80') }}

Note that `minlength` doesn't stop the user from removing characters so that the number entered goes past the minimum, but it does make the value entered into the `<textarea>` invalid. Also note that even if you have a `minlength` value set (3, for example), an empty `<textarea>` is still considered valid unless you also have the `required` attribute set.

### 占位符

此示例设置了占位符。请注意，当您开始在框中键入时，它是如何消失的。

```html
<textarea name="textarea"
   rows="5" cols="30"
   placeholder="Comment text."></textarea>
```

{{ EmbedLiveSample('占位符','600','80') }}

> **备注：** Placeholders should only be used to show an example of the type of data that should be entered into a form; they are _not_ a substitute for a proper {{HTMLElement("label")}} element tied to the input. See [`<input>` labels](/zh-CN/docs/Web/HTML/Element/input#标签) for a full explanation.

### 禁用和只读

This example shows two `<textarea>`s — one of which is `disabled`, and one of which is `readonly`. Have a play with both and you'll see the difference in behavior — the `disabled` element is not selectable in any way (and its value is not submitted), whereas the `readonly` element is selectable and its contents copyable (and its value is submitted); you just can't edit the contents.

> **备注：** In browsers other than firefox, such as chrome, the `disabled` textarea content may be selectable and copyable.

```html
<textarea name="textarea"
   rows="5" cols="30"
   disabled>I am a disabled textarea</textarea>
<textarea name="textarea"
   rows="5" cols="30"
   readonly>I am a readonly textarea</textarea>
```

{{ EmbedLiveSample('禁用和只读','600','80') }}

## 技术概览

<table>
 <tbody>
  <tr>
   <th scope="row"><a href="/zh-CN/docs/HTML/Content_categories">Content categories</a></th>
   <td><a href="/zh-CN/docs/HTML/Content_categories#Flow_content">Flow content</a>, <a href="/zh-CN/docs/HTML/Content_categories#Phrasing_content">phrasing content</a>, <a href="/zh-CN/docs/HTML/Content_categories#Interactive_content">Interactive content</a>, <a href="/zh-CN/docs/HTML/Content_categories#Form_listed">listed</a>, <a href="/zh-CN/docs/HTML/Content_categories#Form_labelable">labelable</a>, <a href="/zh-CN/docs/HTML/Content_categories#form_resettable">resettable</a>, and <a href="/zh-CN/docs/HTML/Content_categories#Form_submittable">submittable</a> <a href="/zh-CN/docs/HTML/Content_categories#Form-associated_">form-associated</a> element.</td>
  </tr>
  <tr>
   <th scope="row">Permitted content</th>
   <td>Text</td>
  </tr>
  <tr>
   <th scope="row">Tag omission</th>
   <td>{{no_tag_omission}}</td>
  </tr>
  <tr>
   <th scope="row">Permitted parents</th>
   <td>Any element that accepts <a href="/zh-CN/docs/HTML/Content_categories#Phrasing_content">phrasing content</a>.</td>
  </tr>
  <tr>
   <th scope="row">Implicit ARIA role</th>
   <td><code><a href="/zh-CN/docs/Web/Accessibility/ARIA/Roles/textbox_role">textbox</a></code></td>
  </tr>
  <tr>
   <th scope="row">Permitted ARIA roles</th>
   <td>No <code>role</code> permitted</td>
  </tr>
  <tr>
   <th scope="row">DOM interface</th>
   <td>{{domxref("HTMLTextAreaElement")}}</td>
  </tr>
 </tbody>
</table>

## 规范

{{Specifications}}

## 浏览器兼容性

{{Compat}}

## 参见

其他与表单相关的元素：

- {{ HTMLElement("form") }}
- {{ HTMLElement("button") }}
- {{ HTMLElement("datalist") }}
- {{ HTMLElement("legend") }}
- {{ HTMLElement("label") }}
- {{ HTMLElement("select") }}
- {{ HTMLElement("optgroup") }}
- {{ HTMLElement("option") }}
- {{ HTMLElement("input") }}
- {{ HTMLElement("keygen") }}
- {{ HTMLElement("fieldset") }}
- {{ HTMLElement("output") }}
- {{ HTMLElement("progress") }}
- {{ HTMLElement("meter") }}
