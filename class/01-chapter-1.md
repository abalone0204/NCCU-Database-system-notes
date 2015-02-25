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

    - 自我定義(self-descripting) :meta-data

    - 把program和data分開(低耦合 loose coupling)

    - 解決在多人使用時transaction的問題

        - 其實也只有多人使用才有transaction的問題
        
        - mysql : 叫做mysql而不叫做oursql，就是因為它本來就是支援單人使用，現在有分transaction 跟沒transaction管理的兩種引擎
    
    - support of multiple views of data

        - View : 虛擬的table，存放在記憶體裡面。

            - 讓使用者看到自己想看，或者有權限看到的東西

### 誰在使用資料庫

- Database administrator(DBA)

    - 權限控管的關係

    - 監測使用

        - ex: 資料庫系統會越來越慢，可能與資料的分佈跟查詢處理有關係，這會牽扯到引擎的運算，所以要定時去監測做最佳化（或甚至重啟）

    - 軟硬體的資源

> Oracle有相關的認證

    
- Database designers (本課程的目標)

    - 確定要放和儲存的資料

    - meta data的設計（資料庫的結構 != 資料結構）

- End users

- Application programmers

### Workers behind the Scene(系統面)

- DBMS system designers and implementers

- Tool developers

- Operators and maintenance personnel

## Advantages of Using the DBMS Approach

- 控制redundancy(balance 讀寫功能)

- 已經提供既有的data structures
    
    - Indexes

    - Buffering and caching

    - Query and GUI

- backup and recovery subsystem

- 完整性的限制(Integrity constraints)

    - 規定的檢查(Rule)

        - Referential integrity constraint

        - Key or uniqueness constraint（看到key就想到uniqueness）

            - 電話沒有唯一性，因為它可以被回收重新讓其他人使用

        - Business rules

        - Inherent rules

- 降低程式開發時間

- Flexibility

- Availability of up-to-date information

- Economies of scale



## A brief History of Database Applications

- 早期的hierarchical and network systems（只剩下早期就資訊化的行業還在用）

    - 台灣的話就還剩下某些銀行業

    - hierarchical : From tree

    - network : From graph

- 關聯式資料庫的出現

    - 分離資料和程式的儲存

    - 提供了很強的數學理論基礎建設在裡面（本課稍後會講到的關聯代數）

- 80年代 
    
    - Oracle 的relational database

    - [Sybase](http://zh.wikipedia.org/zh-tw/Sybase)

- 90年代 

    - Object-oriented的出現

        - 發現只適用於某些領域（ex: 多媒體、醫療影像系統）

        - 間接促成了物件導向的關聯式資料庫(ORM)

    - microsoft跟sybase合作做出sqlserver，但是後來分道揚鑣
    
- 2000年 ~

    - XML的出現

        - 半結構化的資料

        - 效率不快，因為其非結構化

        - 雖然純XML的資料庫也慢慢削減，但是relational database也開始支援XML的markup
    
    - 以資料庫為核心的系統

        - Enterprise resource planning (ERP)

        - Customer relationship management(CRM)

## Summary

- 什麼時候不要用？




























