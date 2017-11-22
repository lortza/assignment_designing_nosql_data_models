## Scenario

You're building a restaurant table reserving app that allows users to reserve tables for specified numbers of people. The app will need to show only tables that are available and the times they are available. The app will need to store reservations under a given name with a phone number and number of guests.

## Schemas
```
# reservation

{
  id: integer,             | indexed and must be unique
  table_ids: array,        |
  name: string,            | must have >= 1 character
  phone: string,           | must have 10 numbers
  person_count             | must be >= 1

}
```

```
# table

{
  id: integer,             | indexed and must be unique
  seats: integer,          | must be >= 1
  available: boolean       | default set to true
}
```

```
# table_assignment

{
  id: integer,             | indexed and must be unique
  table_ids: array,        | must not be null
  reservation_id: integer  | must not be null
}
```
