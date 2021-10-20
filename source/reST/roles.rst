############
Roles
############

Sphinix 使用解析文本角色 (Interpreted text roles) 在文件中插入語意標記。其格式為 *:rolename:`content`*

*****************************
Cross-Referencing syntax
*****************************

<TBD>

Cross-Referencing anything
================================

<TBD>

Cross-Referencing objects
================================

<TBD>

Cross-Referencing arbitrary locations
=========================================

**:ref:**

    | 為了要實行跨區參照任一位置，會使用標準的reST 標籤。也因此所有的標籤在整份文件都是唯一的。
    | 有兩種方式來參照標籤：

    * 如果你將標籤放在Section之前，你可以直接以 *:ref:`label-name`* 來參照。如：

        .. code-block:: reST

            .. ref_test_label_1:

            AutoDoc
            ================

            .. _ref_test_label_2:

            在程式碼中，通常會在文件裡面放入大量的註解。Sphinx支持docstrings的模組擴展。


        example:

        .. code-block:: reST

            這是參照 :ref:`ref_test_label_1` 


        demo:

            這是參照 :ref:`ref_test_label_1` 

        | *:ref:* 會產生一個名為 *AutoDoc* 的連結，來連結跨檔案的標籤。

    * 標籤如果沒有放置在Section前面，仍然可以參照，但必需指定明確的標籤名字。其格為為 *:ref:`link title <label-name>`* 。 

        example:

        .. code-block:: reST

            這是參照2: :ref:`test_ref <ref_test_label_2>`


        demo:

            這是參照2: :ref:`test_ref <ref_test_label_2>`

.. note::

    標籤必需以底線開頭，但參照時不需要底線。可參考上述範例。



Cross-Referencing arbitrary documents
=========================================

還有個方法可參照文件：

**:doc:**

    參照到特定文件；文件路徑可以絕對或相對路徑來參照。舉例來說，如果現行目錄：

    .. code-block::

        | sketches/
        |    index.rst
        |    parrot.rst
        | conf.py
        | people.rst


    | 在index.rst使用參照 *:doc:`parrot`* ，則會將連結指向 *sketches/parrot.rst* 。
    | 如果參照 *:doc:`/people`* 或是參照 *:doc:`../people`* ，則會指向people.rst。
    | 如果沒有明確給定link名稱，則名稱會由參照的文件標題來命名。

    example:

    .. code-block::

        這是文件參照 :doc:`example_code`
        這是絕對文件參照 :doc:`/example_code`
        這是給定名稱的絕對文件參照 :doc:`測試 </example_code>`


    demo:

        | 這是相對文件參照 :doc:`../example_code`
        | 這是絕對文件參照 :doc:`/example_code`
        | 這是給定名稱的絕對文件參照 :doc:`測試 </example_code>`


Referencing downloadable files
=========================================

<TBD>

Cross-Referencing figures by figure number
============================================

<TBD>

Cross-Referencing other items of interest
============================================

<TBD>

******************
Math
******************

<TBD>

******************************
Other semantic markup
******************************

<TBD>

******************************
Substitutions
******************************

<TBD>


