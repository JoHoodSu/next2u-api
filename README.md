# Next2u API
* [Overview](#1-overview)
* [Definitions](#2-definitions)
* [Requirements](#3-requirements)
* [Data Structure](#4-data-structure)
* [Software](#5-software)
* [Roadmap](#6-roadmap)

## 1. Overview
Next2u API is the programming interface of the [Next2u application](https://github.com/JoHoodSu/next2u-app).
## 2. Definitions
## 3. Requirements
## 4. Data Structure
```mermaid
---
title: Next2u
---
erDiagram
    stores {
        int id PK
        int user_id FK
        int latitude
        int longitude
        time creation_time
        string name
        string description
        string phone
    }
    business_hours {
        int id PK
        int store_id FK
        int day
        time open_time
        time close_time
    }
    products {
        int id PK
        string name
        float price
    }
    product_categories {
        int product_id FK
        int category_id FK
    }
    categories {
        int id PK
        string name
    }
    users {
        int id PK
        string name
        int latitude
        int longitude
        time creation_time
    }
    wishlists {
        int id PK
        int user_id FK
        string name
    }
    wishlist_products {
        int wishlist_id FK
        int product_id FK
    }
    stores ||--|{ business_hours : "1+ "
    stores ||--|{ products : "1+"
    products ||--o| product_categories : "0+"
    categories ||--|{ product_categories : "1"
    products ||--o| wishlist_products : "0+"
    wishlists ||--|{ wishlist_products : "1"
    users ||--|{ wishlists : "1"
```
## 5. Software
## 6. Roadmap
> Current Iteration
https://github.com/orgs/JoHoodSu/projects/1/views/2  

> Planning
https://github.com/orgs/JoHoodSu/projects/1/views/4
