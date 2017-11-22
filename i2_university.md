## Scenario

You're building a backend for a university that requires students to be able to log in. Once logged in, the students can view the exam grades for their classes. They should be able to view results by semester. Each semester should only show the classes in which that student is enrolled that semester.

## Schemas

```
# student

{
  id: integer,                | indexed and must be unique
  name: string,               | must be >= 1 char
  email: string,              | must be unique. must have @ symbol.
  password: string,           | must have at least 8 characters
  currently_enrolled: boolean | default set to false
}
```

```
# class

{
  id: integer,                | indexed and must be unique
  name: string,
  code: string,
  student_ids: []
}
```

```
# session

{
  id: integer,                | indexed and must be unique
  name: string                | ex: fall, spring, summer
}
```

```
# semester

{
  id: integer,                | indexed and must be unique
  year: integer
  session_id: integer
}
```

```
# enrollment

{
  id: integer,                | indexed and must be unique
  student_id: integer,
  class_id: integer,
  semester_id: integer

}
```

```
# exam

{
  id: integer,                | indexed and must be unique
  name: string,
  enrollment_id: integer,
  grade: integer,
  date: date
}
```
