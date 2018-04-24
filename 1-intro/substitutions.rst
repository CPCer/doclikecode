替代（Substitutions）
====================

reST语言支持"替代"(\ `参考 <http://docutils.sourceforge.net/docs/ref/rst/restructuredtext.html#substitution-definitions>`_)，即使用 **|替代名称|** 的格式定义的文本和（或）标记对象，类似脚注，使用显式标记文本块定义，例如::

	.. |替代名称| replace:: replacement *实际名称*

或者::

	.. |替代名称| image:: 图片路径.png
             :alt: 图片提示信息

详细内容参见 `reST替代参考 <http://docutils.sourceforge.net/docs/ref/rst/restructuredtext.html#substitution-definitions>`_。

如果想为所有文档使用固定替换，可将所有替代放入 `rst_prolog <http://www.sphinx-doc.org/en/master/config.html#confval-rst_prolog>`_ 、 `rst_epilog <http://www.sphinx-doc.org/en/master/config.html#confval-rst_epilog>`_ 或放入独立文件，并在所有需要的文件里使用 **include** 指令添加进来。（确保添加的文件扩展名与其他文档不同，以免Sphinx将其识别为单独的文档。）
