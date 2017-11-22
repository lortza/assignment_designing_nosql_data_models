You're building an application that requires user login. Once logged in the user has a bunch of profile information and preference settings available to them. They will need to be able to set their birthday, gender, phone number and location (city, state, country). They should be able to provide text to tell about themselves. They also should be able to enable and disable the visibility of their birthday, gender, phone number, and location.

* id: integer
* email: string
  must contain @
* password: password
  must be at least 8 characters and include letters and numbers
* name: string
* bio: text
* stats: document
  * birthday:
  * gender
  * phone number
  * location: document
    * city
    * state
    * country
* show_stats: boolean