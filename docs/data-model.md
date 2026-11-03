# Podatkovni model – Recipe Box

## ER-diagram

```mermaid
erDiagram
    USER ||--o{ RECIPE : owns
    USER ||--o{ COMMENT : writes
    RECIPE ||--o{ COMMENT : has
    RECIPE ||--|{ RECIPE_INGREDIENT : uses
    INGREDIENT ||--o{ RECIPE_INGREDIENT : appears_in

    USER {
        int user_id PK
        string email UK
        string display_name
        string role
    }

    RECIPE {
        int recipe_id PK
        int user_id FK
        string title
        string description
        int servings
        int preparation_time
        string steps
        boolean is_public
    }

    INGREDIENT {
        int ingredient_id PK
        string name UK
        string default_unit
    }

    RECIPE_INGREDIENT {
        int recipe_id PK, FK
        int ingredient_id PK, FK
        decimal quantity
        string unit
    }

    COMMENT {
        int comment_id PK
        int user_id FK
        int recipe_id FK
        string text
        int rating
        datetime created_at
    }
```

## Pojasnilo povezav

1. **User – Recipe (1:N):** En uporabnik lahko ustvari več receptov, vsak recept pa pripada enemu uporabniku. Tuji ključ `user_id` je v tabeli `Recipe`, ker določa lastnika recepta.

2. **User – Comment (1:N):** En uporabnik lahko napiše več komentarjev, vsak komentar pa pripada enemu uporabniku. Tuji ključ `user_id` je v tabeli `Comment`, ker določa avtorja komentarja.

3. **Recipe – Comment (1:N):** En recept ima lahko več komentarjev, vsak komentar pa se nanaša na en recept. Tuji ključ `recipe_id` je v tabeli `Comment`, ker določa recept, ki je komentiran.

4. **Recipe – RecipeIngredient (1:N):** En recept vsebuje eno ali več sestavin, vsaka vrstica v `RecipeIngredient` pa pripada enemu receptu. Tuji ključ `recipe_id` je v tabeli `RecipeIngredient`.

5. **Ingredient – RecipeIngredient (1:N):** Ena sestavina se lahko pojavi v več receptih, vsaka vrstica v `RecipeIngredient` pa se nanaša na eno sestavino. Tuji ključ `ingredient_id` je v tabeli `RecipeIngredient`.

## Povezava M:N

Povezava med `Recipe` in `Ingredient` je M:N, saj lahko recept vsebuje več sestavin, ista sestavina pa se lahko pojavi v več receptih.

Zato uporabimo vezno entiteto `RecipeIngredient`, ki vsebuje tuja ključa `recipe_id` in `ingredient_id` ter dodatna atributa `quantity` in `unit`.