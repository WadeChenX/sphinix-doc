*****
Table
*****

reStructureText 提供兩種表格：網格表(Grid Table)和簡單表(Simple Table)。

網格表
=======

網格中使用的符號有：

* \- 用來分隔行。
* \= 用來分隔標題跟主要內容。
* \| 用來分隔列。
* \+ 用來表示行列交接點。

網格表必需以文字的方式劃出來：

.. code-block:: reST

    +------------------------+------------+----------+----------+
    | Header row, column 1   | Header 2   | Header 3 | Header 4 |
    +========================+============+==========+==========+
    | body row 1, column 1   | column 2   | column 3 | column 4 |
    +------------------------+------------+----------+----------+
    | body row 2             | Cells may span columns.          |
    +------------------------+------------+---------------------+
    | body row 3             | Cells may  | - Table cells       |
    +------------------------+ span rows. | - contain           |
    | body row 4             |            | - body elements.    |
    +------------------------+------------+---------------------+

demo: 

+------------------------+------------+----------+----------+
| Header row, column 1   | Header 2   | Header 3 | Header 4 |
+========================+============+==========+==========+
| body row 1, column 1   | column 2   | column 3 | column 4 |
+------------------------+------------+----------+----------+
| body row 2             | Cells may span columns.          |
+------------------------+------------+---------------------+
| body row 3             | Cells may  | - Table cells       |
+------------------------+ span rows. | - contain           |
| body row 4             |            | - body elements.    |
+------------------------+------------+---------------------+

簡單表
=======

簡單表相對於網格表，少了|跟+符號。只用-和=表示。

.. code-block:: reST

    =====  =====  ======
      Inputs     Output
    ------------  ------
      A      B    A or B
    =====  =====  ======
    False      N/A
    -----  -------------
    True   False  True
    False  True   True
    True   True   True
    =====  =====  ======

demo: 

=====  =====  ======
   Inputs     Output
------------  ------
  A      B    A or B
=====  =====  ======
False      N/A
-----  -------------
True   False  True
False  True   True
True   True   True
=====  =====  ======


