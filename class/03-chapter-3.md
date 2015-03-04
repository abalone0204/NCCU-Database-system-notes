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

- Key(想到唯一性)

    - Superkey of R

    - Removeeing
































