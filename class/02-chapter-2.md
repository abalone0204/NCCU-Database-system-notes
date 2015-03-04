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
































