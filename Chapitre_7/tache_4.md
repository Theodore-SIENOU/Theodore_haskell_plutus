**HC11T4 - Tâche 4 : Instance Container pour Present**

**Sujet**

Implémenter la classe `Container` pour le type `Present`.

---

**Correction complète**

```haskell
-- Main.hs

-- Définition du type Present
data Present a = Empty | Wrap a deriving (Show)

-- Définition de la classe Container (si ce n'est pas déjà fait)
class Container c where
    isEmpty :: c a -> Bool
    contains :: Eq a => c a -> a -> Bool
    replace :: c a -> a -> c a

-- Instance de Container pour Present
instance Container Present where
    -- Vérifie si le présent est vide
    isEmpty Empty = True
    isEmpty (Wrap _) = False

    -- Vérifie si le présent contient un élément spécifique
    contains Empty _ = False
    contains (Wrap x) y = x == y

    -- Remplace le contenu du présent par un nouvel élément
    replace _ newItem = Wrap newItem

-- Fonction principale pour tester
main :: IO ()
main = do
    let emptyPresent = Empty
        gift = Wrap "Teddy"

    putStrLn $ "emptyPresent is empty? " ++ show (isEmpty emptyPresent)
    putStrLn $ "gift is empty? " ++ show (isEmpty gift)

    putStrLn $ "Does gift contain 'Teddy'? " ++ show (contains gift "Teddy")
    putStrLn $ "Does gift contain 'Car'? " ++ show (contains gift "Car")

    let replacedGift = replace emptyPresent "Bike"
    putStrLn $ "Replaced emptyPresent with 'Bike': " ++ show replacedGift
```

---

**Explication**

* `Present a` : type pouvant être vide (`Empty`) ou contenir un élément (`Wrap a`).
* `Container` : classe abstraite pour les containers avec les méthodes `isEmpty`, `contains`, `replace`.
* `instance Container Present` : implémente ces méthodes pour le type `Present` :

  * `isEmpty` : retourne `True` si le présent est vide.
  * `contains` : compare l’élément avec le contenu du présent.
  * `replace` : remplace le contenu par un nouvel élément.
* `main` : teste les fonctions avec un présent vide et un présent contenant un cadeau.

---

**Résultat à l’exécution**

```
emptyPresent is empty? True
gift is empty? False
Does gift contain 'Teddy'? True
Does gift contain 'Car'? False
Replaced emptyPresent with 'Bike': Wrap "Bike"
```

---
