# Moo

Moo is an editor-agnostic markdown live previewer. Once you save your
file, the rendered HTML will automatically get reloaded in your favourite
browser.

![Screenshot](http://i.minus.com/ibnNN6nGKyGKD3.png)

It uses github's own [sundown][sundown] library to provide github
flavored markdown preview. The stylesheet of the preview is extracted
from the github website.

## Installation

```
pip install moo
```

## Usage

Opens preview in browser with server listening on 3000:

```
moo --port 3000 your-doc.markdown
```

Export to HTML only:

```
moo -o exported.html your-doc.markdown
```

## RESTful API

| Action                  | HTTP Method | Request URL                      | Response Body           |
|-------------------------|-------------|----------------------------------|-------------------------|
| Get preview             | GET         | http://localhost:\<port\>        | \<Preview content\>     |
| Get updated content     | POST        | http://localhost:\<port\>/update | \<Rendered body\>       |
| Close server            | DELETE      | http://localhost:\<port\>        |                         |

See [moo.py][moo-src] for more details.

## License

(The MIT License)

Copyright (c) 2012-2013 metaphysiks &lt;i@dingstyle.me&gt;

Permission is hereby granted, free of charge, to any person obtaining
a copy of this software and associated documentation files (the
'Software'), to deal in the Software without restriction, including
without limitation the rights to use, copy, modify, merge, publish,
distribute, sublicense, and/or sell copies of the Software, and to
permit persons to whom the Software is furnished to do so, subject to
the following conditions:

The above copyright notice and this permission notice shall be included
in all copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED 'AS IS', WITHOUT WARRANTY OF ANY KIND, EXPRESS
OR IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF
MERCHANTABILITY, FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT.
IN NO EVENT SHALL THE AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY
CLAIM, DAMAGES OR OTHER LIABILITY, WHETHER IN AN ACTION OF CONTRACT,
TORT OR OTHERWISE, ARISING FROM, OUT OF OR IN CONNECTION WITH THE
SOFTWARE OR THE USE OR OTHER DEALINGS IN THE SOFTWARE.

[sundown]: https://github.com/vmg/sundown
[imd]: https://github.com/suan/instant-markdown-d
[misaka]: https://github.com/FSX/misaka
[moo-src]: moo/moo.py
