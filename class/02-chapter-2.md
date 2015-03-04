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































