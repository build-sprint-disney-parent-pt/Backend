# Disney Parent

## Project Outline

- Pitch: Magic at Your Fingertips- find parents at the park to swap childcare and stroller passes with! Enhance your Disney Experience as parents by connecting with other parents, allowing you to go on all the 'big kid' rides together.

* MVP:

1.  An on-boarding process for parents
2.  On-boarding process for a volunteer experienced business owner
3.  Ability to easily create and post a request (including meeting place/ride and time, and number of kids you have)
4.  Ability to easily edit / delete a question
5.  Ability for anyone to easily search / find posted requests (filter by time, location place, general search)
6.  Ability for a second parent user to log in and respond to the request

- Stretch: Use a notification API like Twilio (https://www.twilio.com/) or Growl (http://growl.info/) for notifications when your request has been answered, or when new requests are posted.

---

## Base URL

- https://disneyparent-backend.herokuapp.com

### Register a Parent

_Method URL: /auth/parents/register_

_HTTP method: [POST]_

### Body

| name        | type   | required | description    |
| ----------- | ------ | -------- | -------------- |
| username    | String | Yes      | Must be unique |
| email       | String | Yes      | Must be unique |
| password    | String | Yes      |                |
| accountType | String | Yes      |                |

_example:_

```
{
  username: "john doe",
  password: "password123",
  email: "johndoe@email.com",
  accountType: "parent"
}
```

### Response

**200**

```
{
"username": "example",
 "password": "example",
 "email": "example@gmail.com", "accountType": "parent",
}
```

---

### Parent Login

_Method URL: /auth/parents/login_

_HTTP method: [POST]_

### Body

| name        | type   | required | description    |
| ----------- | ------ | -------- | -------------- |
| username    | String | Yes      | Must be unique |
| email       | String | Yes      | Must be unique |
| password    | String | Yes      |                |
| accountType | String | Yes      |                |

_example:_

```
{
  username: "john doe",
  password: "password123",
  email: "johndoe@email.com",
  accountType: "parent"
}
```

---

### Parent Post a Request

_Method URL: /posts_

_HTTP method: [POST]_

### Body

| name      | type   | required | description |
| --------- | ------ | -------- | ----------- |
| username  | String | Yes      |             |
| comment   | String | Yes      |             |
| time      | String | Yes      |             |
| parent_id | ID     | Yes      |             |

_example:_

```
{
  "title": "Reqesting Assistance",
  "attraction": "Tornado Ball",
  "children": 5,
  "time": "10 a.m EST",
  "parent_id": 8
}
```

---

### Parent Post a Comment

_Method URL: /comments_

_HTTP method: [POST]_

### Body

| name     | type   | required | description |
| -------- | ------ | -------- | ----------- |
| username | String | Yes      |             |
| comment  | String | Yes      |             |
| post_id  | ID     | Yes      |             |

_example:_

```
{
  "username": "user",
  "comment": "Hello, this is Tony a Cast Member",
  "post_id": 1
}
```

---
