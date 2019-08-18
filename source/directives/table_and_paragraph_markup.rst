**************************
Table and Paragraph markup
**************************

Paragraph-Level Markup
==========================

note
------

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
--------
    
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
--------------
    
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
------------------

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
---------------

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
-------------------

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
-------------------

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
-------------------

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



Table-of-contents Markup
==========================

glossory
---------

| 這道指令必包含由reST definition list所列出的術語(terms)和定義。之後可由 **:term:** 來做索引參照。
| 這個索引定義是全域性。譬如說，Python官方文件通常會定義glossary.rst文件來包含全域的術語定義。
| 也可以參考這份文件的glossary.rst。

code:

.. code-block:: reST

    .. glossary::

        environment
            A structure where information about all documents under the root is
            saved, and used for cross-referencing.  The environment is pickled
            after the parsing stage, so that successive runs only need to read
            and parse new and changed documents.

        source directory
            The directory which, including its subdirectories, contains all
            source files for one Sphinx project.

    * 關鍵字 :term:`environment`
    * 關鍵字 :term:`source directory`
    * 關鍵字 :term:`GitHub`
    * 關鍵字 :term:`Python`

demo:

.. glossary::

   environment
      A structure where information about all documents under the root is
      saved, and used for cross-referencing.  The environment is pickled
      after the parsing stage, so that successive runs only need to read
      and parse new and changed documents.

   source directory
      The directory which, including its subdirectories, contains all
      source files for one Sphinx project.

* 關鍵字 :term:`environment`
* 關鍵字 :term:`source directory`
* 關鍵字 :term:`GitHub`
* 關鍵字 :term:`Python`

productionlist
---------------

| 這道指令主要是包含一段程式碼的 **文法** 。
| **文法** 指令包含名字、冒號和定義，如果定義超過一行的話，必須在換行後，同樣的位置加上冒號並繼續。
| **文法** 裡面不能包含空白行。

.. note::

    **文法** 裡面由於不會做reST 的語語解析，所以當遇到 \* 或\|時，不需要使用跳脫符號\\。

code:

.. code-block:: reST

    .. productionlist::
        try_stmt: try1_stmt | try2_stmt
        try1_stmt: "try" ":" `suite`
                 : ("except" [`expression` ["," `target`]] ":" `suite`)+
                 : ["else" ":" `suite`]
                 : ["finally" ":" `suite`]
        try2_stmt: "try" ":" `suite`
                 : "finally" ":" `suite`    
    

demo:

.. productionlist::
   try_stmt: try1_stmt | try2_stmt
   try1_stmt: "try" ":" `suite`
            : ("except" [`expression` ["," `target`]] ":" `suite`)+
            : ["else" ":" `suite`]
            : ["finally" ":" `suite`]
   try2_stmt: "try" ":" `suite`
            : "finally" ":" `suite`    
    
    
    
    











