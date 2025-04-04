# ELIMINACIONES

[← Regresar a notas](../../README.md) <br>

----

### ▶️ Eliminar un documento
```javascript
db.posts.remove(
  { "_id": ObjectId("6123456789abcdef01234567") }
);
```
----

### ▶️ Eliminar múltiples coincidencias
```javascript
db.posts.remove(
  { "user.name": "Mark Zuckerberg" },
  { multi: true }
);
```
---