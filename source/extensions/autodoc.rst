###############################################################
sphinx.ext.autodoc - Include documentation from docstrings
###############################################################

此外掛模組能將你在模組裡所寫的注釋，透過docstring以半自動的方式加進文件。

.. note::

    由於Sphinx是由python執行，故在尋找模組時，此模組要能被Sphinx找到，這代表搜尋路徑需要列在 sys.path 裡面。故在你的配置裡根據你的需要調整sys.path。

.. warning::

    | 如果載入模組的過程有任何的副作用，當sphinx-build所執行的autodoc也會照樣執行。
    |
    | 如果你撰寫的是script注釋文件(相對於library模組)，請確保主要內容以 ``if __name__ == '__main__'`` 條件保護。


當然，注釋文件需以reST格式寫成，你可以使用常見的Sphinx 標記方法來撰寫。如此方法便不需要再維持兩份不同地方的注釋文件，同時也不需要另外產生並查找API文件。


如果你徧好 NumPy_ 或是 Google_ 樣式的docstring來注釋文件，你可以啟動 :doc:`napoleon` 外掛模組。:doc:`napoleon` 是一種前罝處理功能，用來將你的注釋轉譯成正確的reST格式來讓 **autodoc** 處理。

.. _NumPy: https://numpydoc.readthedocs.io/en/latest/format.html#docstring-standard
.. _Google: https://github.com/google/styleguide/blob/gh-pages/pyguide.md#38-comments-and-docstrings


************************************************
Directives
************************************************

**autodoc** 提供了一些 directives 來分析並轉譯至 **py:modules** 和 **py:class** ，以此類推。
在分析文件時，**autodoc** 會載入相關的來源程式碼並獲取docstring，且將之插入合適的 **py:module** 、 **py:class** 等directive。

| **.. aotomodule::** 
| **.. autoclass::** 
| **.. autoexception::** 

    文件化一module, class或exception，這3個directives會自行將分析後的docstring放入自己所屬的物件：

    .. code-block:: reST

        .. autoclass:: Noodle


    會產生如下：


    .. code-block:: reST

        .. class:: Noodle

            Noodle's docstring


    "auto" directives 也可以包含自己的內容。範例如下：

    .. code-block:: reST

        .. autoclass:: Noodle
           :members: eat, slurp

           .. method:: boil(time=10)

              Boil the noodle *time* minutes.

    **Options**

    **:members:** *(no value or comma seperated list)*

        **autodoc**會對目標 module, class 或 exceptions做文件化。 舉例來說：

        .. code-block:: reST

            .. automodule:: noodle
               :members:


        將文件化所有的members (遞迴)，以及：

        .. code-block:: reST

            .. autoclass:: Noodle
               :members:


        將文件化所有的class members, methods, 和 properties。

        預設來說， **autodoc** 對以下狀況做文件化：

        * private members 。
        * 沒有docstring的members。
        * 繼承自super class。
        * 特別的members。

        如果你的python module未指定 **ignore-module-all** 此flag， **autodoc** 會依照__all__裡面的members依序文件化。

        你可以給予一明確的members list來做文件化。如：

        .. code-block:: reST

            .. automodule:: Noodle
               :members: eat, slurp

    **:undoc-members:** (no value)

        設置此功能會讓 **autodoc** 文件化那些沒有docstring的members

        .. code-block:: reST

            .. automodule:: noodle
               :members:
               :undoc-members:

    **:private-members:** (no value or comma seperated list)

        設置此功能會讓 **autodoc** 文件化那些私有 members (像那些類似命名為 _private 或是 __private)。

        .. code-block:: reST

            .. automodule:: noodle
               :members:
               :private-members:


        也可以給予一明確列表來文件化的members：

        .. code-block:: reST

            .. automodule:: noodle
               :members:
               :private-members: _spicy, _garlickly

    **:special-members:** (no value or comma seperated list)

        設置此功能會讓 **autodoc** 文件化那些特別的 members。(如命名類似為 __special__):

        .. code-block:: reST

            .. automodule:: noodle
               :members:
               :special-members:

        也可以給予一明確的list來文件化特別的members：

        .. code-block:: reST

            .. automodule:: noodle
               :members:
               :special-members: __init__, __name__


    **Options and advanced usage**

        <TBD>

| **.. autofunction::**
| **.. autodecorator::**
| **.. autodata::**
| **.. automethod::**
| **.. autoattribute::**
| **.. autoproperty::**

    這些功能類似 **autoclass** ，但是不提供選項來調整文件化的members。

    **autodata** 和 **autoattribute** 支援 *annotation* 此選項。此選項能控制變數的顯示方式。設置此選項不加參數，則只顯示變數名：

    .. code-block:: reST

        .. autodata:: CD_DRIVE 
           :annotation:

    若設置此選項並加上參數，會視為此變數的值並顯示出來：

    .. code-block:: reST

        .. autodata:: CD_DRIVE 
           :no-value:

    以Sphinx的預設值來說，會試著獲取變數值並顯示出來。

    **no-value** 此選項能不顯示值，取而代之顯示members的型態。

    .. code-block:: reST

        .. autodata:: CD_DRIVE 
           :annotation: = your CD device name

    若 *annotation* 和 *no-value* 同時設置，則 *no-value* 會無效。


************************************************
Configuration
************************************************

<TBD>


************************************************
Docstring preprocessing
************************************************

<TBD>

************************************************
Skipping members
************************************************

<TBD>






