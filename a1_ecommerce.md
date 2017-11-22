## Scenario

Your eCommerce business needs to keep track of products and their prices. The products each belong to a department. The business needs to keep track of revenue as product prices change over time. The business also needs to keep track of receipts of transactions and the number of units each product has in stock.

## Schemas

```
# product

{
  id: integer,                | indexed and must be unique
  name: string
  price: number,
  qty: integer,
  department_id: integer
}
```

```
# department

{
  id: integer,                | indexed and must be unique
  name: string
}
```

```
# customer

{
  id: integer,             | indexed and must be unique
  name: string,            | must have >= 1 char
  email: string,           | must be unique. must have @ symbol.
  password: string,        | must have at least 8 characters
  phone: string,           | must have 10 numbers
  street_1: string,
  street_2: string,
  city: string,
  state_id: integer
  zip: string,
  country_id: integer
}
```

```
# state

{
  id: integer,                | indexed and must be unique
  name: string,
  abbreviation: string
}
```

```
# country

{
  id: integer,                | indexed and must be unique
  name: string
}
```

```
# transaction_item

{
  id: integer,                | indexed and must be unique
  product_id: integer,
  product_price: number,
  qty: integer
  transaction_id: integer
}
```

```
# transaction

{
  id: integer,                | indexed and must be unique
  date: date
  customer_id: integer
  transaction_item_ids: []
  subtotal: number
  taxes_and_crap: number
  total: number
}
```

