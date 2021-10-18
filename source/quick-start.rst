************
Quick Start
************

Start a new project document
============================

可以使用以下指令開新專案(假設已在專案目錄)：

.. code-block:: bat

    sphinx-quickstart
    
開新的專案過程中，會詢問一些問題。在本文件中，例子如下：

::

    (1) Separate source and build directories (y/n) [n] : y
    (2) Project name: test_prj
    (3) Author name(s): test_author
    (4) Project release []: beta-0.1
    (5) Project language [en]: en
    
關於第1個問題，區不區分source和build目錄，目錄結構如下：

+------------------------+-----------------------+
| Non Seperate           | Seperate              |
+========================+=======================+
| $ tree                                         |
+------------------------+-----------------------+
| | .                    | | .                   |
| | \|-- Makefile        | | \|-- Makefile       |
| | \|-- **_build**      | | \|-- **build**      |
| | \|-- _static         | | \|-- make.bat       |
| | \|-- _templates      | | \`-- source         |
| | \|-- conf.py         | |     \|-- _static    |
| | \|-- index.rst       | |     \|-- templates  |
| | \`-- make.bat        | |     \|-- conf.py    |
| |                      | |     \`-- index.rst  |
+------------------------+-----------------------+

這部份就看個人喜好。產生最後結果的目錄，左欄是 **_build** ，右欄是 **build** 。

關於第4個問題，釋出的版本原則上是一字串，可以是 **apha** 、 **beta** 、 **v0.1** .... 等。格式不限制。

關於第5個問題，語言的支援可以看 `language support`_ 。

.. _language support: https://www.sphinx-doc.org/en/master/usage/configuration.html#confval-language

Generate Output
==================

在基本設置結束後，相關的設定都會在 **conf.py** 這個檔案，之後可以再做修改。

而現在可以打指令來產生結果了。指令如下：

.. code-block:: bat

    make html

或是

.. code-block:: bat

    make latexpdf

來產生網頁包或是pdf文件。

.. note::

    產生pdf文件還需要安裝一些程式套件，這部份要看用哪個作業系統。請參閱相關章節。


Switch Theme
================

當output成html格式後，若不喜歡網頁的外觀， **Sphinx** 提供了非常多的外觀模板來做選擇。所有支援的外觀模板可參考 `sphinx theme`_ 。

.. _sphinx theme: https://www.sphinx-doc.org/en/master/usage/theming.html?highlight=theme#themes

可於 *conf.py* 看到一參數：

.. code-block:: reST 

    html_theme = "alabaster"
    
這是預設值，若想要改成不一樣的風格，譬如說 `python 說明文件`_ 的風格：

.. _python 說明文件: https://docs.python.org/2.7/

.. code-block:: python 

    html_theme = "classic"

ReadTheDoc theme
------------------

若想改成ReadTheDoc提供的theme，可以：

.. code-block:: bash

    pip install sphinx-rtd-theme
    
接著，在 *conf.py* 的檔案，開頭修改

.. code-block:: python

    import sphinx_rtd_theme
    html_theme_path = [sphinx_rtd_theme.get_html_theme_path()]
    .............
    html_theme = "sphinx_rtd_theme"

如此就能換成ReadTheDoc風格的theme外觀。


.. _ref_test_label_1:

AutoDoc
================

.. _ref_test_label_2:

在程式碼中，通常會在文件裡面放入大量的註解。Sphinx支持docstrings的模組擴展。

為了使用autodoc，需要在conf.py加入程式碼找尋路徑：

.. code-block:: python

    import os
    import sys
    sys.path.insert(0, os.path.abspath('../example-code'))


接著，在conf.py將extension模組加水來：

.. code-block:: python

    extensions = ["sphinx.ext.autodoc"]


如此便啟動此模組來搜尋相對應的程式碼所在地。

詳情請參考 :doc:`example_code`



Run in Docker image
=============================

| 使用docker image能讓我們快速看到結果，並且可以是跨平台的(如果平台有支援docker技術)。
| 這邊使用一docker image: my_sphinx:v0.0.2 來快速犏譯結果及顯示在web上：

.. code-block::

    docker run  -it --rm -v $(pwd)/sphinix-doc:/doc my_sphinx:0.0.2 docker-web










