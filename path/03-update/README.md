# ACTUALIZACIONES

[← Regresar a notas](../../README.md) <br>

----

### ▶️ Recuperar → Actualizar → Guardar
```javascript
var currentPost = db.posts.findOne({ "_id": ObjectId("6123456789abcdef01234567") });

currentPost.content = "This is the updated content of the post";
currentPost.likes = 20;
currentPost.comments.push({
  comment_id: "c003",
  user: "u113",
  content: "New insightful comment",
  timestamp: new Date()
});

db.posts.update(
  { "_id": ObjectId("6123456789abcdef01234567") },
  currentPost
);
```
----

### ▶️ Modificar directamente con `$set` o `$unset`
```javascript
// Actualizar campos específicos directamente
db.posts.update(
  { "_id": ObjectId("6123456789abcdef01234568") },
  { $set: { content: "Directly updated content", likes: 18 } }
);

// Eliminar un campo específico
db.posts.update(
  { "_id": ObjectId("6123456789abcdef01234568") },
  { $unset: { outdatedField: 1 } }
);
```
----

### ▶️ Modificar múltiples coincidencias
```javascript
// Agregar el campo "platform" a todos los posts de "Mark Zuckerberg"
db.posts.update(
  { "user.name": "Mark Zuckerberg" },
  { $set: { platform: "Facebook" } },
  { multi: true }
);

// Actualizar el estado de posts con pocos likes
db.posts.update(
  { likes: { $lt: 10 } },
  { $set: { status: "LOW_ENGAGEMENT" } },
  { multi: true }
);
```
----

### ▶️ Eliminar un campo para múltiples coincidencias
```javascript
// Remover el campo "status" de todos los posts con estado "LOW_ENGAGEMENT"
db.posts.update(
  { status: "LOW_ENGAGEMENT" },
  { $unset: { status: 1 } },
  { multi: true }
);
```
----