### **HC9T6 - Tâche 6 : Définir un type de données récursif**

#### **Sujet**

> Définir un type de données récursif `Tweet` qui représente un tweet avec :
>
> * du **contenu** (`String`),
> * un **nombre de likes** (`Int`),
> * et une liste de **commentaires**, qui sont eux-mêmes des `Tweet`.

---

###  **Correction complète**

```haskell
-- Fichier : Main.hs

-- Définition d’un type récursif Tweet
data Tweet = Tweet
    { content    :: String      -- Contenu du tweet
    , likes      :: Int         -- Nombre de likes
    , comments   :: [Tweet]     -- Liste de commentaires (tweets imbriqués)
    } deriving (Show)

-- Exemple de tweets
tweet1 :: Tweet
tweet1 = Tweet
    { content = "Hello Haskell world!"
    , likes = 10
    , comments =
        [ Tweet { content = "Nice post!", likes = 3, comments = [] }
        , Tweet { content = "Welcome to functional programming!", likes = 5, comments = [] }
        ]
    }

main :: IO ()
main = print tweet1
```

---

###  **Explication**

* Le type `Tweet` est **récursif**, car le champ `comments` contient une **liste de `Tweet`**.
* Ce genre de structure permet de représenter :

  * un **tweet principal**,
  * des **commentaires imbriqués** (eux-mêmes des tweets).
* `deriving (Show)` permet d’afficher le tweet et ses commentaires directement dans le terminal.

---

### **Résultat à l’exécution**

```
Tweet
  { content = "Hello Haskell world!"
  , likes = 10
  , comments =
      [ Tweet {content = "Nice post!", likes = 3, comments = []}
      , Tweet {content = "Welcome to functional programming!", likes = 5, comments = []}
      ]
  }
```

---
