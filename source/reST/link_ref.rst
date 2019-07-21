*****************
Link & Reference
*****************

HyperLink
=========

reStructureText 會自動將網址文字自動轉換成Hyperlink。

範例：

.. code-block:: reST

    | 這是一個python document的超連接：
    | https://docs.python.org/2.7/
    
demo:

| 這是一個python document的超連接：
| https://docs.python.org/2.7/


External Hyperlink
==================

| 引用/參考(reference) 是簡單參照形式，只能是一個詞語或文字串，且引用的文字不能帶有空格。
| 引用文字連結開頭一定是空白或符號，而結尾帶有_符號，並且之後以空白或符號隔開。
| 若是引用的字串需要空格，則使用\`括起來。

範例：

.. code-block:: reST

    | 這是一個python document的超連接，請參考 ref_ 。
    | 這是一個python document的超連接，請參考 `python mannual`_ 。
    
    .. _ref: https://docs.python.org/2.7/
    .. _python mannual: https://docs.python.org/2.7/    

demo:     
        
| 這是一個python document的超連接，請參考 ref_ 。
| 這是一個python document的超連接，請參考 `python mannual`_ 。
    
.. _ref: https://docs.python.org/2.7/
.. _python mannual: https://docs.python.org/2.7/    

Internal Hyperlink
==================
    
內部引用就像是標籤，於網頁上可跳至引用的部份，不過僅限同一文件(頁)。

範例：

.. code-block:: reST   
 
    這是一個python document的超連接，請參考 引用_ 。

    這裡是其它內容。

    這裡是其它內容。

    這裡是其它內容。

    這裡是其它內容。
    
    .. _引用: 
    
    這裡引用其它文件1。    

    這裡引用其它文件2。

    這裡引用其它文件3。
    
demo:     
        
這是一個python document的超連接，請參考 引用_ 。

這裡是其它內容。

這裡是其它內容。

這裡是其它內容。

這裡是其它內容。
    
.. _引用: 
    
這裡引用內容1。    

這裡引用內容2。

這裡引用內容3。

Anonymous hyperlink
===================

| 引用的文字中如果帶有符號或空白等字元，可使用此匿名連結的方式。
| 引用文字片段可使用兩個反引號符號括起來，結尾以__符號結束。

範例：

.. code-block:: reST  

    這是一個python document的 `study the python`__。

    .. __: https://docs.python.org/2.7/

demo: 

這是一個python document的 `study the python`__。

.. __: https://docs.python.org/2.7/

Indirect Hyperlink
===================

間接連結是基於匿名連結的方式做延伸。

範例：

.. code-block:: reST  

    這是一個 python_ document的 `study the python`__。

    .. _python: https://docs.python.org/2.7/
    .. __: python_

demo:

這是一個 python_ document的 `study the python`__。

.. _python: https://docs.python.org/2.7/
.. __: python_

Implicit Hyperlink
===================

由於章節、標題、註腳和引用參考都會產生超連結，同份rst檔案可以引用這些連結。這即為隱式超連結。

範例：

.. code-block:: reST 

    | 關於reStructure Text中的外部連結的說明，可參考 `External Hyperlink`_ 以獲得更多資訊。
    | 這是 `註腳連結`_ 。
    | 這是 `文件1`_。

demo:

| 關於reStructure Text中的外部連結的說明，可參考 `External Hyperlink`_ 以獲得更多資訊。
| 這是 `註腳連結`_ 。
| 這是 `文件1`_。    

Substitution Reference
=======================

| 替換引用就是利用定義好的指令替換對應的文字或圖片。
| 指令以\|符號括住，前後都需空白。

範例：

.. code-block:: reST 

    這個 |logo| 是github的logo，我最愛的語言是 |favo_lang| 。

    .. |logo| image:: https://help.github.com/assets/images/site/favicon.ico
    .. |favo_lang| replace:: Python

demo:

這個 |logo| 是github的logo，我最愛的語言是 |favo_lang| 。

.. |logo| image:: https://help.github.com/assets/images/site/favicon.ico
.. |favo_lang| replace:: Python


Footnote Reference
==================

註腳引用，有幾種方式：

* 手工序號。
* 填入\#符號，自動生成編號。
* 填入\*符號，自動生成符號。

| 手工序號可以和自動符號\#結合，做為編號的起始。
| \#符號可在後面接個名稱，此名稱就會生成一個連結。供其它地方使用。

範例：

.. code-block:: reST 

    | 註腳引用 -- 數字 [1]_
    | 註腳引用 -- 數字 [#]_
    | 註腳引用 -- 數字 [#]_
    | 註腳引用 -- 數字&連接 [#註腳連結]_
    | 註腳引用 -- 符號 [*]_
    | 註腳引用 -- 符號 [*]_
    | 註腳引用 -- 符號 [*]_

    .. [1] 註腳內容 -- 數字
    .. [#] 註腳內容 -- 數字
    .. [#] 註腳內容 -- 數字
    .. [#註腳連結] 註腳內容--數字，這是 註腳連結_
    .. [*] 註腳內容 -- 符號
    .. [*] 註腳內容 -- 符號
    .. [*] 註腳內容 -- 符號

demo:

| 註腳引用 -- 數字 [1]_
| 註腳引用 -- 數字 [#]_
| 註腳引用 -- 數字 [#]_
| 註腳引用 -- 數字&連接 [#註腳連結]_
| 註腳引用 -- 符號 [*]_
| 註腳引用 -- 符號 [*]_
| 註腳引用 -- 符號 [*]_

.. [1] 註腳內容 -- 數字
.. [#] 註腳內容 -- 數字
.. [#] 註腳內容 -- 數字
.. [#註腳連結] 註腳內容--數字，這是 註腳連結_
.. [*] 註腳內容 -- 符號
.. [*] 註腳內容 -- 符號
.. [*] 註腳內容 -- 符號

Citation Reference
==================

引用參考跟註腳有些類似。不過通常會放在頁面的結尾處。

範例：

.. code-block:: reST 

    引用這些文件： [文件1]_, [文件2]_。

    .. [文件1] 參考文件1
    .. [文件2] 參考文件2

demo:

引用這些文件： [文件1]_, [文件2]_。

.. [文件1] 參考文件1
.. [文件2] 參考文件2

Comments
=========

| 註釋以..開頭，後面接註釋即可。可以是多行內容，多行時每行開頭加一個空白。
| 註釋內容不會呈現在最終文件上。譬如網頁或是pdf文件。

範例：

.. code-block:: reST 

    | 這是本文1。
    | 這是本文2。

    ..
     這是註釋內容1。
     這是註譯內容2。
 
demo:

| 這是本文1。
| 這是本文2。

..
 這是註釋內容1。
 這是註譯內容2。


















    
    
    