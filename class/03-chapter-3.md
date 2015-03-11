# Chapter 3 Relational Model

## Outline


## Concepts

- 將資料視為一組關聯(relation) -> tables

- Table of values = Relations

    - Row 

        - Tuple : 較學術的用字

    - Table name and column names

        - 解釋資料的面向

        - Column: attribute

## Domains, Attributes, Tuples, and Relations

- Domain D

    - Set of atomic values

- __Atomic__

    - Each value indivisible

- Specifying a domain

    - Data type : 宣告值域

- __Relation schema__ R
    
    - Denoted by R(A_1, A2,... ,A_n)

    - Name R and a list of attributes A_1, A_2,..., A_n
- Attribute A


- Degree(or arity) of a relation

    - 有幾種attribute

- Relation(or relation state)

    - Set of n-tuples `r= {t_1, t_2, ..., t_m}`

        - Why `m`?

        - `t = <v1, v2, ... , vn>`
    
    - Mathmatical relation of degree n on the domains dom(A1), dom(A2)... , dom(An)

    - Subset of the Cartesian product of domains that define R:

        - `r(R) 包含於(dom(A1)x dom(A2) x ... x dom(An))`
    
    - Ordering of tuples in a relation

        - __Elements have no order among them__

        - 實務上是有排序，但實際上的tuple並沒有順序，因為它是一個集合，數學上的集合是沒有順序可言的

        - Question: 那column(attribute)的順序呢？

            - SQL在insert資料時候不輸入欄位名稱，按照順序一樣可以輸正確的資料（不過不是好習慣）

            - 最好的做法是每次都記得attribute的名字，而不是記得它在第幾行

    - Alternative definition of relation(可略)

        - Column-store 比較適合分析性的工作


### Characteristics of Relations

- `NULL` : 空值

    - Value unknown -> 連是否存在都不知道

    - Value exists but is not available

    - Attribute does not apply to this tuple(also known as value undefined)

        - 這個屬性並不適用於這個tuple

        - 通常暗示設計有問題(某些attribute絕對不會出現在某些tuple)

        - e.q : 在病例中加入是否懷孕過的欄位（但是男性不會懷孕，所以這一欄都會是NULL，這樣代表設計上其實是有問題的）

- Values and NULLs in tuples

    - Flat relational model

        - First normal form assumption(1NF)

        - 不能有多值屬性

    - Multivalued attributes(多值屬性)

        - 一個屬性有很多個值

        - Must be represented by seperate relations

    - Composite attributes(複合屬性)

        - Question: Address?

        - 看需求


### Constraints

- Constraints

    - rule : 規則

    - Type 1

        - DBMS can help (Required by data model and database)

    - Type 2

        - DBMS can't do much(business logic)

- Key(想到唯一性)

    - Superkey of R

    - Removeeing

#### Domain Constraints

- Domain: 值域

    - Numeric

    - Characters

    - Booleans

    - Fixed-length strings(`CHAR`)

        - 優點：通常比較快

        - 缺點：缺乏彈性

        - e.q: `CHAR(10)`: 一定會湊滿十個，沒有的話會塞空白

    - Variable-length strings(`VARCHAR`)

        - 優點：彈性

        - 缺點：可能會比較慢

        - e.q: `VARCHAR(10)`: 最多十個，沒有滿也不會補空白

    - Date, time, timestamp

        - Take advantage of built-in types data

    - Money

    - Other special data types

        - BLOB(pronounce: Ber-Lar-Ber): used to store sveral kb/mbs of `binary data`

            - e.q: pictures, video, audio...

        - CLOB(Clar-Ber): store large chracters data

            - e.q: documents


#### Key Constraints and Constraints on NULL Values

- No two tuples can have the same comnination of values for all their attributes

- Superkey

- Key

    - Two distinct tuples in any state of relation(time) cannot have identical values for all attributes in key(在所有時間內都要是`唯一`的)

    - Minima superkey

- Candidate key

    - 同一筆資料中有許多欄位都具有唯一性

- Primary key of the relation

    - Designated among candidate keys

    - Underline attribute


### Integrity, Referential Integrity, and Foreign Keys

- Entity integrity constraint(實體完整性限制)

    - No primary key value can be NULL（Primary key一定不能是Null）

- Referential integrity constraint(參考完整性限制)

    - 針對`fk`(foreign key)

    - fk一定要指定某個table的pk（也可能指回自己的pk），不能指向找不到的值

        - e.q : 

            - fk可以是Null，但是fk如果為5，而要指向的pk卻不存在5時，就不行

            - 因為這樣違反了實體完整性限制(entity integrity constraint)
    
- Foreign key rules

    - domain要與指向的PK相同

- integrity constraints全部會交由DBMS來檢查

- Semantic integrity constraints

    - Triggers

        - Active Database(當加入某些資料滿足某些條件時，資料庫會主動(active)去做一些事情)

    - Assertions

        - Complex checking

### Update Operations, Transactions, and Dealing with Constraint Violations

- Retrievals and updates

- Basic operations that change the state of relations in the database

    - Insert

    - Delete

    - Update(modify)

### Relational model graph

- `Figure 3.6`

- `Figure 3.7`（缺乏domain，需要另外寫下來）

    - 畫底線的: pk

    - 出去的一定是fk

### Insert Operation

- 花時間，因為需要許多檢查（可能會違反任一constraints）

### Delete Operation

- 可能會讓fk找不到值（Referential integrity constraint)

- Solution
    
    - Restrict: reject deletion

    - Cascade: 連坐

### Summary

- 見ppt






















