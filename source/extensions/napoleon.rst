#######################################################################
sphinx.ext.napoleon - Support for Numpy and Google style docstrings
#######################################################################

**********************************
Overview
**********************************

**reStructureText** 的格式如下：

.. code-block:: reST

    :param path: The path of the file to wrap
    :type path: str
    :param field_storage: The :class:`FileStorage` instance to wrap
    :type field_storage: FileStorage
    :param temporary: Whether or not to delete the file when the File
       instance is destructed
    :type temporary: bool
    :returns: A buffered writable file descriptor
    :rtype: BufferedFileStorage

**reStructureText** 是不錯，不過看起來內容過於擁擠，難以閱讀。相同內容以 `Google Python Style`_ 來重寫如下：


.. code-block:: reST

    Args:
        path (str): The path of the file to wrap
        field_storage (FileStorage): The :class:`FileStorage` instance to wrap
        temporary (bool): Whether or not to delete the file when the File
            instance is destructed

    Returns:
        BufferedFileStorage: A buffered writable file descriptor


看起來比較清楚，對吧？

Napoleon這個外掛的前置處理功能可以轉換 `Numpy`_ 和 `Google`_ 兩種型式成reStructureText能分析的格式。
轉換過程是Sphinx開始文件化的過程中途才會處理，故你不需擔心來源程式碼的docstring會被改寫。



.. _Google Python Style: https://google.github.io/styleguide/pyguide.html
.. _Google: https://google.github.io/styleguide/pyguide.html#Comments
.. _Numpy: https://numpydoc.readthedocs.io/en/latest/format.html#docstring-standard


Getting Started
======================================

1. 在 *conf.py* 啟動 **napoleon** 外掛：

   .. code-block:: reST

        # conf.py

        # Add napoleon to the extensions list
        extensions = ['sphinx.ext.napoleon']

2. 用 *sphinx-apidoc* 做文件化：

   .. code-block:: shell

        $ sphinx-apidoc -f -o docs/source projectdir


Docstrings
===========================================

Napoleon 解析所有能讓 autodoc 解析的docstring，這包含了：

* modules
* classes
* attributes
* methods

在docstring裡面，特別的 `Docstring Sections`_ 也會被轉譯成 reStructureText。


Docstring Sections
=============================================

以下是支援的section headers：

* Args *(alias of Parameters)*
* Arguments *(alias of Parameters)*
* Attention
* Attributes
* Caution
* Danger
* Error
* Example
* Examples
* Hint
* Important
* Keyword Args *(alias of Keyword Arguments)*
* Keyword Arguments
* Methods
* Note
* Notes
* Other Parameters
* Parameters
* Return *(alias of Returns)*
* Returns
* Raise *(alias of Raises)*
* Raises
* References
* See Also
* Tip
* Todo
* Warning
* Warnings *(alias of Warning)*
* Warn *(alias of Warns)*
* Warns
* Yield *(alias of Yields)*
* Yields

Google vs Numpy
======================================

Napoleon 支援 Numpy 和 Google 兩種格式。這兩種格式主要差別為 Google 使用縮排來區別 section，而 Numpy 是使用底線來區別 section。

Google style:

.. code-block:: python

    def func(arg1, arg2):
        """Summary line.

        Extended description of function.

        Args:
            arg1 (int): Description of arg1
            arg2 (str): Description of arg2

        Returns:
            bool: Description of return value

        """

        return True


Numpy style:

.. code-block:: python

    def func(arg1, arg2):
        """Summary line.

        Extended description of function.

        Parameters
        ----------
        arg1 : int
            Description of arg1
        arg2 : str
            Description of arg2

        Returns
        -------
        bool
            Description of return value

        """
        return True


Numpy 需要較長的列數，而 Google 則需要較寬的行。
Google在讀取較少且簡單的docstring容易閱讀，而 Numpy 則在內容長且深的docstring容易閱讀。

Numpy 和 Google 這兩種不應該混用。為你的專案選擇一個樣式並堅持它。


.. seealso::

    完整的範例：

    :doc:`../example_code`


Type Annotation
========================================

`PEP484`_ 提供了在 Python 程式碼裡標準型態的表示方式，這是一種在docstring裡直接表示型態的方式。
根據 `PEP484`_ 表示的方式有一好處就是型態檢查工具以及 IDE 可以對程式碼做靜態分析。
`PEP484`_ 之後延伸的 `PEP526`_ ，也引進了類似的方式來標記變數。

Python3 程式碼標記方式配合 Google style的標記：

.. code-block:: python

    def func(arg1: int, arg2: str) -> bool:
        """Summary line.

        Extended description of function.

        Args:
            arg1: Description of arg1
            arg2: Description of arg2

        Returns:
            Description of return value

        """
        return True

        class Class:
            """Summary line.

            Extended description of class

            Attributes:
                attr1: Description of attr1
                attr2: Description of attr2
            """

            attr1: int
            attr2: str



Google style 在 docstring 顯示型態的方式：

.. code-block:: python

    def func(arg1, arg2):
        """Summary line.

        Extended description of function.

        Args:
            arg1 (int): Description of arg1
            arg2 (str): Description of arg2

        Returns:
            bool: Description of return value

        """
        return True

        class Class:
            """Summary line.

            Extended description of class

            Attributes:
                attr1 (int): Description of attr1
                attr2 (str): Description of attr2
            """


.. note::

    Sphinx 在文件裡不支援且不會顯示 `Python2/Python3 compatible annotation`_

.. _PEP484: https://www.python.org/dev/peps/pep-0484/
.. _PEP526: https://www.python.org/dev/peps/pep-0526/https://www.python.org/dev/peps/pep-0526/
.. _Python2/Python3 compatible annotation: https://www.python.org/dev/peps/pep-0484/#suggested-syntax-for-python-2-7-and-straddling-code


**********************************
Configuration
**********************************

以下是 napoleon 預設所使用的配置。這些都是可在 *conf.py* 設定。請確保 **sphinx.ext.napoleon** 在 *conf.py* 是啟動的。

.. code-block:: python

    # conf.py

    # Add any Sphinx extension module names here, as strings
    extensions = ['sphinx.ext.napoleon']

    # Napoleon settings
    napoleon_google_docstring = True
    napoleon_numpy_docstring = True
    napoleon_include_init_with_doc = False
    napoleon_include_private_with_doc = False
    napoleon_include_special_with_doc = True
    napoleon_use_admonition_for_examples = False
    napoleon_use_admonition_for_notes = False
    napoleon_use_admonition_for_references = False
    napoleon_use_ivar = False
    napoleon_use_param = True
    napoleon_use_rtype = True
    napoleon_preprocess_types = False
    napoleon_type_aliases = None
    napoleon_attr_annotations = True



**napoleon_google_docstring**

    * True: 開啟分析 Google style docstrings。
    * False: 關閉分析 Google style docstring。
    * Default: True

**napoleon_numpy_docstring**

    * True: 開啟分析 Numpy style docstrings。
    * False: 關閉分析 Numpy style docstring。
    * Default: True

**napoleon_include_init_with_doc**

    * True: 從 class docstring中分別列出 __init__ docstrings。
    * False: 關閉此功能。
    * Default: False。

    **If True:**

    .. code-block:: python


         def __init__(self):
            """
            This will be included in the docs because it has a docstring
            """

            def __init__(self):
                # This will NOT be included in the docs

**napoleon_include_private_with_doc**

    * True: 在docstring中包含私有 members (像是 _member)。
    * False: 關閉此功能。
    * Default: False。

    **If True:**

    .. code-block:: python

         def _included(self):
            """
            This will be included in the docs because it has a docstring
            """
            pass

         def _skipped(self):
            # This will NOT be included in the docs
            pass

**napoleon_include_special_with_doc**

    * True: 在docstring中包含特別的 members (像是 __membername__)。
    * False: 關閉此功能。
    * Default: False。

    **If True:**

    .. code-block:: python

        def __str__(self):
            """
            This will be included in the docs because it has a docstring
            """
            return unicode(self).encode('utf-8')

        def __unicode__(self):
            # This will NOT be included in the docs
            return unicode(self.__class__.__name__)


**napoleon_use_admonition_for_examples**

    <TBD>

**napoleon_use_admonition_for_notes**

    <TBD>

**napoleon_use_admonition_for_references**

    <TBD>

**napoleon_use_ivar**

    * True: 對變數使用 :ivar: 。
    * False: 對變數使用 .. attribute\:\: 。
    * Default: False。

**napoleon_use_param**

    * True: 對函式變數使用 :param:
    * False: 對函式變數使用 :parameter:
    * Default: True

**napoleon_use_keyword**

    * True: 對函式關鍵字使用 :keyword:
    * False: 對函式關鍵字使用 :keyword arguments:
    * Default: True

**napoleon_use_rtype**

    * True: 回傳型態使用 :rtype:
    * False: 回傳型態內嵌於回傳的描述。
    * Default: True

**napoleon_preprocess_types**

    <TBD>

**napoleon_type_aliases**

    <TBD>

**napoleon_attr_annotations**

    <TBD>

**napoleon_custom_sections**

    <TBD>












