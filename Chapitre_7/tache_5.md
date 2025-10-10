**HC11T5 - Tâche 5 : Fonction `guessWhat'sInside` pour Container**

**Sujet**

Créer une fonction `guessWhat'sInside` qui prend un `Container` et vérifie si un élément spécifique s’y trouve.

---

**Correction complète**

---

```haskell
-- Main.hs

class Container c where
    isEmpty :: c a -> Bool
    contains :: Eq a => c a -> a -> Bool
    replace :: c a -> a -> c a

data Present a = Empty | Wrap a deriving (Show)

instance Container Present where
    isEmpty Empty = True
    isEmpty (Wrap _) = False

    contains Empty _ = False
    contains (Wrap x) y = x == y

    replace _ newItem = Wrap newItem

-- Ici on ajoute Show a dans le contexte
guessWhatsInside :: (Container c, Eq a, Show a) => c a -> a -> String
guessWhatsInside container item =
    if contains container item
        then "Yes! It contains the item: " ++ show item
        else "Nope! Item not found: " ++ show item

main :: IO ()
main = do
    let gift1 = Wrap "Teddy"
        gift2 = Empty

    putStrLn $ guessWhatsInside gift1 "Teddy"
    putStrLn $ guessWhatsInside gift1 "Car"
    putStrLn $ guessWhatsInside gift2 "Bike"
```

---

**Explication de la correction** :

* Le problème venait de `show item`.
* Pour utiliser `show`, Haskell a besoin de savoir que le type `a` est une instance de `Show`.
* On ajoute donc `Show a` dans le contexte de la fonction :

```haskell
guessWhatsInside :: (Container c, Eq a, Show a) => c a -> a -> String
```
