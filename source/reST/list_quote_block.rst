************************
List & quoted-like block
************************

Quoted-like block
==================

段落之間需要空白行。而line-block可以不增加多餘的空白行來顯示多段落。

樣式：

.. code-block:: reST

    | 段落1。
    | 段落2。
    | 段落3。
    
demo: 

| 段落1。
| 段落2。
| 段落3。

.. note::

    這種樣式適合在清單要顯示多行時使用。
    
Literal blocks
===============

文字區塊是正文中插入的一段訊息文字。使用時，正文後面使用:: 接著空行，接著插入文字區塊。

文字區塊必需縮排，結束後，下個段落沒有縮排。

樣式：

.. code-block:: reST

    下面是文字塊內容：
    ::
        文字區塊第一行
        第二行
        第三行
    
    新的段落。

demo:

下面是文字塊內容：
::
    文字區塊第一行
    第二行
    第三行
    
新的段落。

Doctest Blocks
==============

文件測試區塊是交互式的python 執行結果，以>>>開始，一個空行結束。

.. code-block:: reST

    >>> print "這是文件測試區塊"
    這是文件測試區塊

demo:

>>> print "這是文件測試區塊"
這是文件測試區塊

Bullet list
===========

符號清單的使用非常容易。只需在前面加上：

.. code-block:: reST

    - * +

這3種字元即可。

符號清單樣式：

.. code-block:: reST

    * 項目1
    * 項目2
    * 項目3，使用巢狀清單
    
        * 項目a
        * 項目b
        
    * 項目4
    
    - 減號1
    
    + 加號1
    
demo:

* 項目1
* 項目2
* 項目3，使用巢狀清單
   
    * 項目a
    * 項目b
        
* 項目4

- 減號1

+ 加號1

Enumerated Lists
================

列舉清單即順序列表，可用不同的符號來表示：

* 阿拉伯數字：1, 2, 3, ...。
* 大寫字母：A - Z。
* 小寫字母：a - z。

可以為清單加入前綴和後綴字元：

- .後綴： \\"1.\\", \\"2.\\", \\"3.\\" ...
- ()括號： (1), (2), (3)
- )後綴： 1), 2), 3)

列舉清單可使用\\"#\\" 字元來自動生成。

列舉清單樣式：

.. code-block:: reST
    
    1. 項目1
    #. 項目2
    #. 項目3
    
    (c) 項目1
    (#) 項目2
    (#) 項目3

    
    B) 項目1
    #) 項目2
    #) 項目3

demo:

1. 項目1
#. 項目2
#. 項目3
    
(c) 項目1
(#) 項目2
(#) 項目3
    
B) 項目1
#) 項目2
#) 項目3

Definition list
================

定義列表即解釋列表，用於名詞解釋。解釋的段落要縮排。而巢狀定義可以縮排來實現。

.. code-block:: reST

    定義1
        這是定義1的內容
    
    定義2
        | 這是定義2的內容。  
        | 這是定義2的第二行。
    
        定義3
            這是定義3的內容。
        
demo:

定義1
    這是定義1的內容
    
定義2
    | 這是定義2的內容。  
    | 這是定義2的第二行。
    
    定義3
        這是定義3的內容。


Option Lists
============

選項列表是類似二列的表格，左邊是參數，右邊是描述訊息。當參數過長時，參數選項和描述訊息各佔一行。

選項與參數之間有一個空格，參數選項與描述訊息之間至少二個空格。

樣式：

.. code-block:: reST

    -a            command-line option "a"
    -b file       options can have arguments
                    and long descriptions
    --long        options can be long also
    --input=file  long options can also have
                    arguments
    /V            DOS/VMS-style options too

demo:

-a            command-line option "a"
-b file       options can have arguments
              and long descriptions
--long        options can be long also
--input=file  long options can also have
              arguments
/V            DOS/VMS-style options too

Field Lists
============

欄位列表是以標注欄位而成的清單： 

.. code-block:: reST

    :fieldname: Field content
        
常用於python文件如：

code:

.. code-block:: reST

    def my_function(my_arg, my_other_arg):
        \\"\\"\\"A function just for me.

        :param my_arg: The first of my arguments.
        :param my_other_arg: The second of my arguments.

        :returns: A message (just for me, of course).
        \\"\\"\\"

demo:

def my_function(my_arg, my_other_arg):
    \\"\\"\\"A function just for me.

    :param my_arg: The first of my arguments.
    :param my_other_arg: The second of my arguments.

    :returns: A message (just for me, of course).
    \\"\\"\\"
    






