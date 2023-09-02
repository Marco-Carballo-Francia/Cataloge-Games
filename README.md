# Base de Datos para Videojuegos

## Tablas de relaciones existentes

- **_videogames_**
- **_genres_**
- **_plataforms_**
- **_stores_**
- **_ratings_**
- **_tags_**

---

### VIDEOGAMES **(ED)**

1. videogames_id **:** `UUID` **_(PK)_**
1. name **:** `VARCHAR(150)` **_(UQ)_**
1. slug **:** `VARCHAR(160)` **_(UQ)_**
1. date **:** `DATE`
1. update **:** `DATE`
1. added (descargas) **:** `INT`
1. imagen **:** `URL`
1. video **:** `URL`
1. screenshots **:** `URL`
1. rating **:** `INT` **_(FK)_** _relacion uno a uno_
1. plataforms **:** `INT` **_(FK)_** _relacion mucho a mucho_
1. genres **:** `INT`  **_(FK)_** _relacion mucho a mucho_
1. tags **:** `INT` **_(FK)_** _relacion mucho a mucho_
1. stores **:** `INT` **_(FK)_** _relacion mucho a mucho_

### RATINGS **(ED)**

1. rating_id **:** `UUID` **_(PK)_**
1. rating **:** `FLOAT`
1. stars `OBJ` **:** {
    1. star1_count **:** `INT`
    1. star2_count **:** `INT`
    1. star3_count **:** `INT`
    1. star4_count **:** `INT`
    1. star5_count **:** `INT`
}
1. top **:** `FLOAT`
1. count_rating **:** `INT`

### PLATAFORMS **(EC)**

1. plataforms_id **:** `UUID` **_(PK)_**
1. name **:** `VARCHAR(25)` **_(UQ)_**
1. requeriment **:** `TEXT`

### GENRES **(EC)**

1. genres_id **:** `UUID` **_(PK)_**
1. name **:** `VARCHAR(40)` **_(UQ)_**
1. slug **:** `VARCHAR(50)` **_(UQ)_**

### TAGS **(EC)**

1. tags_id **:** `UUID` **_(PK)_**
1. name **:** `VARCHAR(50)` **_(UQ)_**
1. slug **:** `VARCHAR(60)` **_(UQ)_**

### STORES **(EC)**

1. stores_id **:** `UUID` **_(PK)_**
1. name **:** `VARCHAR(30)` **_(UQ)_**
1. slug **:** `VARCHAR(40)` **_(UQ)_**
