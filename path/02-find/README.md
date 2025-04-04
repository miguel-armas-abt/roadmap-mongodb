# CONSULTAS

[← Regresar a notas](../../README.md) <br>

----

### ▶️ Consultar por _id
```javascript
var post = db.posts.findOne(
  { "_id": ObjectId("6123456789abcdef01234567") }
);
```
----

### ▶️ Consultar por campos
```javascript
db.posts.find({
  "user.name": "Linus Torvalds",
  "likes": 15
});
```
----

### ▶️ Consultar diferente de
```javascript
db.posts.find({
  "likes": { $ne: 15 }
});
```
----

### ▶️ Consultar ocultando campos
```javascript
db.posts.find(
  {},
  { "content": 1, "timestamp": 1, "_id": 0 }
);
```
----

### ▶️ Consultar elementos entre
```javascript
db.posts.find(
  { "likes": { $gte: 10, $lte: 20 } },
  { "content": 1, "likes": 1, "_id": 0 }
).pretty();
```
----

### ▶️ Consultar por RegEx
```javascript
db.posts.find({ "content": /example/ });
db.posts.find({ "content": /^This is/ });
db.posts.find({ "content": /post$/ });
```
----
