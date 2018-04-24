其他问题（Gotchas）
====================

在编辑reST文档时，可能会遇到如下问题：

* **行内标记分隔：** 如上所述，行内标记字符之间须使用非文本字符分隔开，否则应使用转义的反斜杠。`参考详细内容 <http://docutils.sourceforge.net/docs/ref/rst/restructuredtext.html#substitution-definitions>`_。
* **行内标记不可嵌套：** 形如*see :func:`foo`*是不可实现的。
