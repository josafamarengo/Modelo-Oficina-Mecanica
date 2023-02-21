# Modelagem Oficina Mecânica

```mermaid
erDiagram
    VEHICLE {
        string id
        string model
        string year
        string license_plate
        string color
    }
    MECHANIC {
        string id
        string name
        string address
        string specialty
    }
    SERVICE {
        string id
        string description
    }
    PART {
        string id
        string name
        float price
    }
    SERVICE -||{ ORDER_ITEM : "includes"
    PART -||{ ORDER_ITEM : "includes"
    ORDER_ITEM {
        string id
        integer quantity
        float service_price
        float part_price
    }
    ORDER_ITEM ||--o{ ORDER : "belongs to"
    ORDER {
        string id
        date issue_date
        date delivery_date
        float total_value
        string status
        date deadline
    }
    ORDER ||--o{ VEHICLE : "refers to"
    ORDER ||--o{ MECHANIC : "assigned to"
    ORDER ||--o{ CUSTOMER : "ordered by"
    CUSTOMER {
        string id
        string name
        string phone
        string address
    }
```