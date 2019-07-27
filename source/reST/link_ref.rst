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
| 同份文件如果用了太多匿名連結，可能是一場災難。因為匿名連結的找尋對映是針對整份文件，會因為某些匿名找不到而錯亂。

範例：

.. code-block:: reST  

    這是一個python document的 `study the python`__ 。

    .. __: https://docs.python.org/2.7/

demo: 

這是一個python document的 `study the python`__ 。

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


Image & Figure
===============

Image
------

文字內容或段落可以插入圖片元素。

其插入圖片的寫法範例如下：

.. code-block:: reST 

    .. image:: picture.jpeg
        :height: 100px
        :width: 200 px
        :scale: 50 %
        :alt: alternate text
        :align: right

圖片的關鍵字如下：

alt: 替換文字。
    | 當應用程序無法顯示圖片時，會顯示圖片的一個簡短描述。
height: 高度。
    | 指定圖片需要的長度，單位可以是px(像素), em, ex, in, cm, mm, pt, pc等。不指定就是原圖片高度。
    | 這個會跟scale關鍵字一起計算。最後的結果相當於height * scale。
    | 例如：height為200px，scale為50%, 會等於height為100px但不指定scale(預設100%)。
width: 寬度。
    | 指定圖片需要的寬度，單位如height關鍵字。不指定就是原圖片寬度。
    | 算法如height關鍵字。
scale: 比例，單位是 % (可寫或不寫)
    | 縮放因子，預設100%。
align: 對齊方式。
    | 可以是"top", "middle", "bottom", "left", "center", 或 "right" 。
    | 相當於html語法中<img>裡面的align屬性。
    | 而值: "top"、"middle"、"bottom"用於控常圖片的緃向對齊方式，只對inline圖片有效。
    | 而值："left"、"center"、"right"用於控制圖片的橫向對齊方式，允許圖片浮動，文字圍繞圖片。
    | 不過俱體行為仍看瀏覽器或渲染的應用程序而定。
target: 引用名稱或是連結。
    | 將圖片變為超連結來使用("可點擊")。參數是URI或是包含 _ 的引用名稱。


範例：

.. code-block:: reST 

    格式一： 圖片在非內嵌時的置中對齊。

        .. image:: ../_static/github.png
            :height: 100px
            :width: 100px
            :alt: 這是github logo
            :align: center

    格式二： 圖片在內嵌時的文繞圖呈現。

        | GitHub Logo: |octocat|。這個logo是一張範例圖片。

    .. |octocat| image:: ../_static/github.png
        :scale: 50%
        :alt: 這是github logo
        :align: top
    
    格式三： inline圖片在表格式的情況。

    +------------------------+------------+----------+
    | Header row, column 1   | Header 2   | Header 3 |
    +========================+============+==========+
    | body row 1, column 1   | column 2   | column 3 |
    +------------------------+------------+----------+
    | body row 2             |                       |
    +------------------------+                       |
    | body row 3             |  |octocat_big|        |
    +------------------------+                       |
    | body row 4             |                       |
    +------------------------+------------+----------+

    .. |octocat_big| image:: ../_static/github_big.jpg
        :scale: 20%
        :alt: 這是github big logo
        :align: top

    格式四： 有連結的圖片。

        | 連結圖片： |link_pic|_

    .. |link_pic| image:: ../_static/github.png
    .. _link_pic: https://github.com/

        | 連結圖片2： |link2_pic|

    .. |link2_pic| image:: ../_static/github.png
        :scale: 50%
        :alt: 這是github logo
        :target: `HyperLink`_


demo:

格式一： 圖片在非內嵌時的置中對齊。

.. image:: ../_static/github.png
    :height: 100px
    :width: 100px
    :alt: 這是github logo
    :align: center

格式二： 圖片在內嵌時的文繞圖呈現。

    | GitHub Logo: |octocat|。這個logo是一張範例圖片。

.. |octocat| image:: ../_static/github.png
    :scale: 50%
    :alt: 這是github logo
    :align: top
    
格式三： inline圖片在表格式的情況。

+------------------------+------------+----------+
| Header row, column 1   | Header 2   | Header 3 |
+========================+============+==========+
| body row 1, column 1   | column 2   | column 3 |
+------------------------+------------+----------+
| body row 2             |                       |
+------------------------+                       |
| body row 3             |  |octocat_big|        |
+------------------------+                       |
| body row 4             |                       |
+------------------------+------------+----------+

.. |octocat_big| image:: ../_static/github_big.jpg
    :scale: 20%
    :alt: 這是github big logo
    :align: top

格式四： 有連結的圖片。

    | 連結圖片： |link_pic|_ 。連結到github網站

.. |link_pic| image:: ../_static/github.png
.. _link_pic: https://github.com/

    | 連結圖片2： |link2_pic|。連結到本文的HyperLink標題

.. |link2_pic| image:: ../_static/github.png
    :scale: 50%
    :alt: 這是github logo
    :target: `HyperLink`_

Figure
------

| figure 元素包含了image data (含蓋了image的屬性)，以及一個可選擇的標題，和一個選擇性的說明(legend)。
| 標題段落之前和說明(legend)之前都需要有空行，若說明(legend)之前沒有標題，則標題的位置可使用空注釋符號 .. 。
| figure 元素不適合像image元素一樣，可以使用 `Substitution Reference`_ 。
| figure 元素可以直接使用超連結(HyperLink)。
| figure 元素指令支持 `Image`_ 所有屬性。這些屬性除了align以外，都會傳給 `Image`_。
| 以下是figure的獨立的屬性：

align: 對齊方式。
    | 可以是 ``left`` 、 ``center`` 或 ``right`` 。
    | figure的橫向對齊，允許圖片浮動及五字圍繞它。具體行為取決於瀏覽器或其它渲染程式。

figclass: <缺>
    | <缺>
    
figwidth: figure的寬度。
    | 限定使用行的寬度可以是支持的單位(eg: px)，或是寬度百分比。
    | 除了上述的方式，還可以使用``image``，不過這需要 `Python 圖片庫`_ 支援。若指定的圖片不存在或是沒有 `Python 圖片庫`_，則此欄位會忽略。
    
.. _`Python 圖片庫`: http://www.pythonware.com/products/pil/
    

    
.. code-block:: reST 
    
    +---------------------------+
    |        figure             |
    |                           |
    |<------ figwidth --------->|
    |                           |
    |  +---------------------+  |
    |  |     image           |  |
    |  |                     |  |
    |  |<--- width --------->|  |
    |  +---------------------+  |
    |                           |
    |The figure's caption should|
    |wrap at this width.        |
    +---------------------------+


範例：

.. code-block:: reST 

    這是github的logo。

    .. figure:: ../_static/github_big.jpg
        :scale: 25%
        :align: center
        :alt: 這是圖片訊息
    
        這是一個圖片標題。
    
        說明(legend)包含了標題(caption)以外的所有元素。在這個例子裡，包含一個段落以及以下的表格：
    
        +-----------------------+-----------------------+
        | 標題 1                | 標題 2                |
        +=======================+=======================+
        | 內容 1                | 內容 a                |
        +-----------------------+-----------------------+
        | 內容 2                | 內容 b                |
        +-----------------------+-----------------------+
        | 內容 3                | 內容 c                |
        +-----------------------+-----------------------+


demo:

這是github的logo。

.. figure:: ../_static/github_big.jpg
    :scale: 25%
    :align: center
    :alt: 這是圖片訊息
    
    這是一個圖片標題。
    
    說明(legend)包含了標題(caption)以外的所有元素。在這個例子裡，包含一個段落以及以下的表格：
    
    +-----------------------+-----------------------+
    | 標題 1                | 標題 2                |
    +=======================+=======================+
    | 內容 1                | 內容 a                |
    +-----------------------+-----------------------+
    | 內容 2                | 內容 b                |
    +-----------------------+-----------------------+
    | 內容 3                | 內容 c                |
    +-----------------------+-----------------------+


    


    
    
    