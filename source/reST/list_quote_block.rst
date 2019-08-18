************************
List & quoted-like block
************************

Block Quotes
=============

* 區塊引用是通過縮排來實現的，引用區塊要在前面的段落基礎上縮排。
* 通常引用結尾會加上出處(attribution)，出處的文字開頭是-, --, ---符號，後面加上出處訊息。
* 區塊引用可以使用空的注釋..符號，分隔上下的區塊引用。
* 區塊引用和出處都需要新的空白行隔開。除非使用 `Line Block`_，

demo:

下面是引用的內容：

    "真的勇士，敢於面對慘淡的人生，敢於正視淋漓的鮮血。"
    
        --- 魯迅
    
..

    "人生的意志和勞動將創造奇跡般的奇跡。"
    
    -- 涅克拉索

..

    | "對於那些覺得不吸煙就會安全的人來說，二手煙是一個巨大的安全隱患，自電子煙問世以來，
    | 總是遭到人們的質疑，現在越來越多的證據證明電子煙沒有二手煙危害是無害的。
    | 不僅幫助自己戒煙還包括幫助非吸煙者戒煙。"
    |   - 美國國家科學院報告
    

Line Block
===========

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
    
Literal Blocks
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

Bullet List
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

Definition List
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
    






