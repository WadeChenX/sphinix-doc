**************************
Paragraph-level markup
**************************

note
======

| .. note::
|   注意的樣式

code:

.. code-block:: reST

    .. note::
        
        這是一個 **注意** 的段落。
        
demo:
    
.. note::
        
    這是一個 **注意** 的段落。

    
warning
========
    
| .. warning::
|   警告的樣式

code:

.. code-block:: reST

    .. warning::
        
        這是一個 **警告** 的段落。
        
demo:
    
.. warning::
        
    這是一個 **警告** 的段落。
    
versionadded
==============
    
| .. versionadded:: <version>
|   描述功能是在哪個版本導入。以斜體標示。

code:

.. code-block:: python

    def my_function(my_arg, my_other_arg):
        \\"\\"\\"A function just for me.

        :param my_arg: The first of my arguments.
        :param my_other_arg: The second of my arguments.

        :returns: A message (just for me, of course).
        
        \\"\\"\\"
    
    .. versionadded:: 2.5

demo: 

def my_function(my_arg, my_other_arg):
    \\"\\"\\"A function just for me.

    :param my_arg: The first of my arguments.
    :param my_other_arg: The second of my arguments.

    :returns: A message (just for me, of course).
    
    \\"\\"\\"


.. versionadded:: 2.5

versionchanged
=====================

| .. versionchanged:: <version>
| 描述此功能在哪個版本有變更。

code:

.. code-block:: python

    def my_function(my_arg):
        \\"\\"\\"A function just for me.

        :param my_arg: The first of my arguments.

        :returns: A message (just for me, of course).
        
        \\"\\"\\"

    .. versionchanged:: 2.6

demo:

def my_function(my_arg):
    \\"\\"\\"A function just for me.

    :param my_arg: The first of my arguments.

    :returns: A message (just for me, of course).
    
    \\"\\"\\"

.. versionchanged:: 2.6

deprecated
=====================

| .. deprecated:: <version>
|     描述功能在哪個版本捨棄。

.. code-block:: python

    def my_function(my_arg):
        \\"\\"\\"A function just for me.

        :param my_arg: The first of my arguments.

        :returns: A message (just for me, of course).
        
        \\"\\"\\"

    .. deprecated:: 2.7

demo:

def my_function(my_arg):
    \\"\\"\\"A function just for me.

    :param my_arg: The first of my arguments.

    :returns: A message (just for me, of course).
    
    \\"\\"\\"

.. deprecated:: 2.7

seealso
=====================

| .. seealso::
|     描述功能的詳細資訊，另可參照其它資料。

.. code-block:: reST

    os.listdir( *path* )
        回傳當下目錄裡的子目錄。
    
    .. seealso:: 

        可參照原生python文件：https://docs.python.org/2/library/os.html?highlight=listdir#os.listdir

demo:

os.listdir( *path* )
    回傳當下目錄裡的子目錄。
    
.. seealso:: 

    可參照原生python文件：https://docs.python.org/2/library/os.html?highlight=listdir#os.listdir

rubric
=====================

| .. rubric:: <title>
|     段落的標題。此種標題不會被建在 **Table of contents** 裡面當連結。

code:

.. code-block:: reST

    .. rubric:: Will we ever control the world with our minds?

    | For decades, controlling computers by thought was the stuff of science fiction. 
    | But now we are tantalisingly close to a breakthrough. 
    | The question is, does it create more problems than it solves?


demo:

.. rubric:: Will we ever control the world with our minds?

| For decades, controlling computers by thought was the stuff of science fiction. 
| But now we are tantalisingly close to a breakthrough. 
| The question is, does it create more problems than it solves?

hlist
=====================

| .. hlist::
|     設定欄位，將緃向清單轉換成多欄的清單。方向是先由上而下，再由左至右。

code:

.. code-block:: reST

    .. hlist::
        :columns: 3

        * A list of
        * short items
        * that should be
        * displayed
        * horizontally

demo:

.. hlist::
    :columns: 3

    * A list of
    * short items
    * that should be
    * displayed
    * horizontally

