# API de Álbumes con Gin

Este pequeño servicio HTTP en Go utiliza el framework [Gin](https://github.com/gin-gonic/gin) para exponer un API REST que gestiona una colección en memoria de álbums musicales.

---

## 📦 Modelo de datos

```go
type album struct {
  ID     string `json:"id"`     // Identificador único
  Title  string `json:"title"`  // Título del álbum
  Artist string `json:"artist"` // Nombre del artista
  Year   int    `json:"year"`   // Año de publicación
}

var albums = []album{
  {ID: "1", Title: "Familia", Artist: "Camila Cabello", Year: 2022},
  {ID: "2", Title: "21", Artist: "Adele", Year: 2011},
  {ID: "3", Title: "The Eminem Show", Artist: "Eminem", Year: 2002},
  {ID: "4", Title: "Meteora", Artist: "Linkin Park", Year: 2003},
  {ID: "5", Title: "25", Artist: "Adele", Year: 2015},
}


## 🚀 Endpoints

| Método | Ruta          | Descripción                          |
| ------ | ------------- | ------------------------------------ |
| GET    | `/albums`     | Devuelve la lista completa de álbums |
| POST   | `/albums`     | Añade un nuevo álbum (recibe JSON)   |
| GET    | `/albums/:id` | Devuelve un álbum por su `id`        |
