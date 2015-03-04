# Chapter 2 Overview of Database Languages and Architecture

## Basic DBMS Architecture

> 類似於傳統的主從式架構

- Client module

- Server module

## Data model

- 模型(model):真實世界中資料的縮影

- 抽象化(data abstraction)

- Categories:
    
    - High-level(Conceptural data models)

        - 概念性的程式 -> 給人看的

    - Low-level(Physical data models)

        - 實體的程式 -> 給機器看的 

    - Representational data models

        - 接近於上兩者之間

    - Entity

    - Attribute

    - Relationship:
        - Entity-Relationship models用圖形的方式來描述實體之間的關係

    - Relational data models

    - Physical data models : SQL

### Schemas, Instances, and Database State

- Database schema
    
    - Description of a database
    
    - 綱目: 對行跟列的解釋（row, column）

    - meta-data的重要性

        - 從mis角度看商品越來越多、公司越來越大
    
    - 設計: User (DBA)

    - 管理: DBMS

- Database state

    - 資料庫在__任何時間點__的status
    
        - 分為合法和非法的狀態( Initial, valid, invalid state)

        - DBMS會確保這一點，現在通常已經不會遇到，通常都是schema設計的問題
    
    - Initial state

    - Valid state 

        - Satisfies the structure and constraints specified in the schema
    
- Schema evolution

    - Bio-information 領域

### Three-schema architecture

- Internal Schema

    - Inside DBMS

    - 通常不會碰到

- Conceptual Schema

    - User

- External View

    - End user

#### Data independence

- Benifit
    
    - 可以不用被同個DBMS綁死(Capable)

### DBMS Languages

- Data definition language(DDL)

    - 定義schema的語言

- ~~Storage definition language(SDL)~~
    
    - 定義internal的schema，不過因為它是internal所以不太會用到

    - 即SQL的標準

- View definition language(VDL)

    - Closed to DDL

- Data manipulation language(DML)

    - 操作資料的語言

    - retrieval, insertion, deletion, modifcation

> SQL includes DDL and DML
> 不過SQL不只包含這兩個（其實也可以說它包含VDL）
> 但是它不能去指定SDL這一類比較底層資料如何儲存的部分

- Figure 2.3

    - `System Catalog/ Data Dictionary` : 存放meta data(schema)的地方

    - `Runtime Database Processor` : 資料庫的引擎

        - Read and Write

    - `Stored Database` : 一個很特別的file(sub-)system

    - `Precompiler` : 將SQL內嵌在高階語言中，所以要先經過precompile才能通過compiler將高階語言編譯完成

        - 不過已經比較少見了

        - 現在常見：ODBC or JDBC -> Query Compiler

            - Open DataBase Connection

            - Java DataBase Connection

    - `Parametric User`

        - `Stored procedure` -> `Compile Procedures`

        - 使用者

            - 讓不太懂SQL或PG的人也能使用（通過stored procedure）

            - program也可以使用（e.q 常用的查詢

        - 大部份都是用特定的語言寫的（非高階語言）

            - e.q:

                - Oracle: PL SQL

                - Micosoft: T SQL

> ###Common paths to use DB today?
> 1. application programs -> query & DML compiler => Query Optimizer -> DB Engine
> 2. Interactive Query UI -> Query Compiler -> Query Optimizer -> DB Engine
> 3. Stored Procedure -> DB Engine

### Database System Utilities

- Performance monitoring

    - provide statistics to the DBA

#### Centralized and Cliient/Server Architectures for DBMSs

- Centralized 

    - 全部都放在同一台機器上(include server and client)

- Client/Server (2 tiers)
    
    - Figure 2.6

    - Client : 即放application programs的地方，越來越複雜，演變出後來的3-tier architecture

    - Server : 提供硬體、軟體服務，這裏就是DBMS

        - open database connectivity: 永遠記得檢查driver有沒有裝 :P

- Three-tier(Presentation layer, Business Logic Layer, Database Services Layer) 

    - Client : GUI, web inter face
    
    - Application Server or Web Server

        - 大部份應用程式的邏輯在這裡（e.q : apache）

    - Database Server : DBMS

### Classification of Database Management Systems

- Data model 

    - Relational

    - Object

    - Hierarchical and network (legacy)

    - Native XML DBMS

- Number of users

- Number of sites 
    
    - Centralized

    - Distributed

        - Homogeneous : 都是同樣的機器

        - Hetergeneous: 機器可能是不一樣的
    
    - Cost

        - Open source

        - Different types of licensing

            - Refer: http://en.wikipedia.org/wiki/Free_software_license



























