****************
Install Sphinx 
****************

Overview
=========

Sphinx是以Python開發完成的，並且支援 Python 3.5+ 。
這份文件使用的sphinx-build版本是 **2.1.2** 。

Linux
======

Debian/Ubuntu
--------------

* 若系統用的是Python3，安裝 ``python3-sphinx`` 。
* 若系統用的是Python2，安裝 ``python-sphinx`` 。

.. code-block:: bash

    $ apt-get install python3-sphinx

如果Python套件不存在，這裡也會順便安裝Python套件。

RHEL, CentOS
-------------

使用yum安裝 python-sphinx。

.. code-block:: bash

    $ yum install python-sphinx

如果Python套件不存在，這裡也會順便安裝Python套件。  

MacOS
======

可以使用一些套件管理程式 `Homebrew`_ 、 `MacPorts`_ 或 `Anaconda`_ 來安裝 Sphinx 。

.. _Homebrew: https://brew.sh/
.. _MacPorts: https://www.macports.org/
.. _Anaconda: https://www.anaconda.com/distribution/#macos

Homebrew
--------

.. code-block:: bash

    $ brew install sphinx-doc
    
MacPorts
-------- 

* 若系統用的是Python3，安裝 ``python36-sphinx`` 。
* 若系統用的是Python2，安裝 ``python27-sphinx`` 。

.. code-block:: bash

    $ sudo port install py36-sphinx
    
可以用以下指令來設定執行路徑：

.. code-block:: bash

    $ sudo port select --set python python36
    $ sudo port select --set sphinx py36-sphinx
    
    
Anaconda
-------- 

.. code-block:: bash

    $ conda install sphinx
    
Windows
========    

由於Python預設是不會裝進windows系統的， 故我們必需先確定系統上是否以有python。

可以開啟 *Windows Command Prompt* 來輸入以下指令：

.. code-block:: bat

    python --version
    
如果有安裝python的話，應該會顯示python的版本。如果沒有安裝的話，可以搜尋網路上的安裝教學或是參照 [Hitchhikers Guide to Python’s]_ 來安裝Python和套件管理程式 **PyPI(pip)** 。

** Windows上必須安裝 Python3 。**

.. [[Hitchhikers Guide to Python’s]] https://docs.python-guide.org/

安裝完Python3和pip之後，就可以透過pip安裝sphinx。

Installation from PyPI
=======================

Sphinx 是以Python套件的形式來做發佈，故安裝的方式可以使用PyPI(pip)。

在Linux 或是MacOS的系統上，可以打開Terminal，輸入以下指令：

.. code-block:: bash

    $ pip install -U sphinx
    
在Windows的作業系統，可以打開 Windows Command Prompt，並輸入以下指令：

.. code-block:: bat

    C:\> pip install -U sphinx
        
如果安裝成功，可以試著打下面的指令：

.. code-block:: bash

    sphinx-build --version

如果一切都沒問通，照理說是可以看到Sphinx套件的版本號。 

