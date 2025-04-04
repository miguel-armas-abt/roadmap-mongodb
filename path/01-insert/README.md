# INSERT

[← Regresar a notas](../../README.md) <br>

----

### 📋 Tipos de dato

```javascript
var myDocument = {
  stringValue: "Hello world!",
  numberValue: 20,
  floatValue: 20.5,
  booleanValue: true,
  dateAndTimeValue: ISODate("2016-04-29T15:49:03.598Z"),
  currentDateAndTimeValue: new Date(),
  dateValue: ISODate("2015-10-21")
};
```

----

### ▶️ Inserciones

```javascript
use db_posts;
show collections;

var postOne = {
  user: {
    "user_id": "u78910",
    "name": "Linus Torvalds"
  },
  content: "This is an example of Facebook post",
  timestamp: "2025-04-04T12:00:00Z",
  likes: 15,
  comments: [
    {
      comment_id: "c001",
      user: "u111",
      content: "¡Great post!",
      timestamp: "2025-04-04T12:05:00Z"
    }
  ]
};

var postTwo = {
  user: {
    "user_id": "u78911",
    "name": "Mark Zuckerberg"
  },
  content: "This is an example of Facebook post",
  timestamp: "2025-04-05T12:00:00Z",
  likes: 12,
  comments: [
    {
      comment_id: "c002",
      user: "u112",
      content: "I like the apples too",
      timestamp: "2025-04-05T12:05:00Z"
    }
  ]
};

db.posts.insert([postOne, postTwo]);
db.posts.find().pretty();
```