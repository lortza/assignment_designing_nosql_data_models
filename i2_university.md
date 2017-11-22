## Scenario

You're building a backend for a university that requires students to be able to log in. Once logged in, the students can view the exam grades for their classes. They should be able to view results by semester. Each semester should only show the classes in which that student is enrolled that semester.

## Schemas
semester
class
exam
grade

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
# exam

{
  id: integer,                | indexed and must be unique
  name: string
  class_id: integer
  student_id: integer
  grade: integer
  date: date
}
```
