# Text styling #

`fpdf2` supports setting _emphasis_ on text : **bold**, __italics__ or <u>underlined</u>.

Bold & italics require using dedicated fonts for each style.

For the standard fonts (Courier, Helvetica & Times), those dedicated fonts are configured by default.
Using other fonts means that their variants (bold, italics)
must be registered using `add_font` (with `style="B"` and `style="I"`).


## set_font ##

Setting emphasis on text can be controlled by using `set_font(style=...)`

```python
from fpdf import FPDF

pdf = FPDF()
pdf.add_page()
pdf.set_font("Times", size=36)
pdf.cell(w=50, txt="This")
pdf.set_font(style="B")
pdf.cell(w=50, txt="is")
pdf.set_font(style="I")
pdf.cell(w=50, txt="a")
pdf.set_font(style="U")
pdf.cell(w=50, txt="PDF")
pdf.output("style.pdf")
```


## write_html ##

[`write_html`](HTML.md) allows to set emphasis on text through the `<b>`, `<i>` and `<u>` tags:

```python
pdf.write_html("""<B>bold</B>
                  <I>italic</I>
                  <U>underlined</U>
                  <B><I><U>all at once!</U></I></B>"""
)
```
