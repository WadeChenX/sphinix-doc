#######################################################################
sphinx.ext.viewcode - Add links to hightlighted source code
#######################################################################

此外掛能得知程式碼物件的描述 ( .. class\:\:, .. function\:\:, etc) 並且試著搜尋來源碼來查找出處。
如果有找到，會以一HTML頁面顯示，並在物件描述上加上連結參照。在參考來源碼時，也有一連結來回到原來的位置。

.. warning::

    基本上， **viewcode** 這外掛會在做連結時載入相對應的 module。如果module有副作用的話，在 sphinx-build 啟動時也是會執行的。

    如果對 script (相對於 library) 做文件化，確保主要功能皆被 ``if __name__ == '__main__'`` 這條件保護。

    如果你有一些 module 不想被載入，你可以使用 viewcode-find-source 事件指定給 viewcode 。

    如果 viewcode_follow_imported_members 啟動，需使用 viewcode-follow-imported 事件來解決載入後的 attributes。

這外掛只支援 HTML 相關的建置像是 html, applehelp, devhelp, htmlhelp, qthelp 等。但不支援單頁 html。
預設上 epub 也不支援。

*******************
Configuration
*******************

**viewcode_follow_imported_members**

<TBD>

**viewcode_enable_epub**

<TBD>

**viewcode-find-source(app, modname)**

<TBD>

**viewcode-follow-imported(app, modname, attribute)**

<TBD>
