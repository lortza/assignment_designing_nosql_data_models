## Scenario

You're building an application that requires user login. Once logged in the user has a bunch of profile information and preference settings available to them. They will need to be able to set their birthday, gender, phone number and location (city, state, country). They should be able to provide text to tell about themselves. They also should be able to enable and disable the visibility of their birthday, gender, phone number, and location.

## Soft Schema
```
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
      state: string,       | derived from other selection table
      country: string,     | derived from other selection table
    }
  }
  show_stats: boolean,     | default set to true
}
```



