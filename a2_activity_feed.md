## Scenario

You're building an activity feed for a social media site. The feed must display a chronological list of activities for the current user's friends. These activities could potentially be any action performed on the site including:

* uploading a photo
* changing their profile
* friending another user
* commenting
* liking
* etc...

Further, you only want to display activities for users that the current user interacts with frequently.

## Schemas

```
# user

{
  id: integer,             | indexed and must be unique
  email: string,           | must be unique. must have @ symbol.
  password: string,        | must have at least 8 characters
  name: string,            | must have >= 1 char
  bio: text,               | must have >= 1 char
  stats: {
    birthday: date,        |
    gender: string,        | derived from other selection table
    phone number: string,  | must have 10 digits. all numbers.
    location: {
      city: string,        |
      state_id: integer,   |
    }
  }
  show_stats: boolean,     | default set to true
  friend_ids: []
}
```

```
# state

{
  id: integer,             | indexed and must be unique
  name: string,            | must have >= 1 char
}
```

```
# country

{
  id: integer,             | indexed and must be unique
  name: string,            | must have >= 1 char
  country_id: integer      |
}
```

```
# activity

{
  id: integer,                | indexed and must be unique
  type_id: integer,
  date: date,
  user_id: integer,
  description: varchar
}
```

```
# activity_type

{
  id: integer,                | indexed and must be unique
  name: string                | set list, ex: photo, status,

}
```
