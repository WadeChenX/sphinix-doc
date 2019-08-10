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


