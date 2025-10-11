### **HC8T10 – Deriving Show pour Book**

**Sujet :**
En utilisant `deriving Show`, définir un type `Book` avec les champs :

* `title :: String`
* `author :: String`
* `year :: Int`

Créer une instance de `Book` et l’afficher avec l’instance `Show`.

---

###  **Correction complète**

```haskell
-- Définition du type Book avec deriving Show
data Book = Book
    { title  :: String
    , author :: String
    , year   :: Int
    } deriving (Show)

-- Fonction principale pour tester
main :: IO ()
main = do
    let myBook = Book "Learn You a Haskell" "Miran Lipovača" 2011
    print myBook
```

---

###  **Explication**

* `deriving (Show)` permet à Haskell de **générer automatiquement** une instance de la classe `Show` pour le type `Book`.
* Cela signifie que tu peux utiliser `print` pour afficher une valeur de type `Book` directement.
* `Book` utilise la **syntaxe d’enregistrement** (avec `{}`) pour plus de clarté.

---

###  **Résultat attendu**

```
Book {title = "Learn You a Haskell", author = "Miran Lipovača", year = 2011}
```

---
