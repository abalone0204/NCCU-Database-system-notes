## Chapter 1 

### Database

- 資料庫：放資料的地方

- 放什麼資料？

    - 有關聯的(related)

    - 真實的(fact)

    - 真實世界裡的某個縮影or面向 Miniworld of discourse(UoD)

- 為特定目的建立的

> Data warehouse: 資料倉儲
> 跟資料庫不同，資料庫以「交易」為中心(OLTP) -> 重視Write
> 資料倉儲裡面放著好幾個「資料庫」
> 目的在於存放歷史資料，以「分析」為中心(OLAP) -> 重視Read

### 資料庫管理系統

- Database management system(DBMS)

- collection of programs

- enables users to create and maintain a database

### 定義資料庫（設計）

- 定義資料的:

    - 型態(types): integer, string...

    - 結構(structures)

        - 不需要跟資料庫系統講清楚，因為用SQL溝通時不會使用到array

    - 限制(constraints)

        - 不是limitations，而是指資料庫中規則的constraints

### 元資料(Meta-data)

- data用來描述現實世界裡的fact -> meta-data則是用來描述data的data

- 設計資料庫的主要地方，根據meta-data來建立資料庫

### Manipulating

- Query and update

- Generate reports （這堂課不會講）

> manipulate為什麼負面？


### 什麼時候可以用到資料庫

- 使用DBMS的好處

    - 自我定義(meta-data)

    - 把program和data分開(低耦合 loose coupling)

    - 解決在多人使用時transaction的問題

        - 其實也只有多人使用才有transaction的問題
        
        - mysql : 叫做mysql而不叫做oursql，就是因為它本來就是支援單人使用，現在有分transaction 跟沒transaction管理的兩種引擎
    
    - support of multiple views of data

        - View : 虛擬的table，存放在記憶體裡面。

            - 讓使用者看到自己想看，或者有權限看到的東西


    




































