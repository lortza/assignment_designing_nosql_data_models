## Scenario

Your eCommerce business needs to keep track of products and their prices. The products each belong to a department. The business needs to keep track of revenue as product prices change over time. The business also needs to keep track of receipts of transactions and the number of units each product has in stock.

## Schemas
prices
transactions
units in stock

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
