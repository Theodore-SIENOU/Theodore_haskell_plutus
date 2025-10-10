**HC11T3 - Tâche 3 : Classe de type Container pour Box**

**Sujet**

Définir une classe de type `Container` avec les méthodes :

* `isEmpty` : vérifie si le container est vide
* `contains` : vérifie si un élément donné est présent
* `replace` : remplace le contenu par un nouvel élément

Puis implémenter une instance pour le type `Box`.

---

**Correction complète**

```haskell
-- Main.hs

-- Définition du type Box
data Box a = Box (Maybe a) deriving (Show)

-- Définition de la classe Container
class Container c where
    isEmpty :: c a -> Bool
    contains :: Eq a => c a -> a -> Bool
    replace :: c a -> a -> c a

-- Instance de Container pour Box
instance Container Box where
    -- Vérifie si la boîte est vide
    isEmpty (Box Nothing) = True
    isEmpty (Box (Just _)) = False

    -- Vérifie si la boîte contient un élément spécifique
    contains (Box Nothing) _ = False
    contains (Box (Just x)) y = x == y

    -- Remplace le contenu de la boîte par un nouvel élément
    replace _ newItem = Box (Just newItem)

-- Fonction principale pour tester
main :: IO ()
main = do
    let emptyBox = Box Nothing
        filledBox = Box (Just 42)

    putStrLn $ "emptyBox is empty? " ++ show (isEmpty emptyBox)
    putStrLn $ "filledBox is empty? " ++ show (isEmpty filledBox)

    putStrLn $ "Does filledBox contain 42? " ++ show (contains filledBox 42)
    putStrLn $ "Does filledBox contain 7? " ++ show (contains filledBox 7)

    let replacedBox = replace emptyBox 99
    putStrLn $ "Replaced emptyBox with 99: " ++ show replacedBox
```

---

**Explication**

* `Box a` : type pouvant contenir un élément (`Just a`) ou être vide (`Nothing`).
* `Container` : classe de type abstraite pour les containers, avec trois méthodes : `isEmpty`, `contains`, `replace`.
* `instance Container Box` : implémente les méthodes pour le type `Box`.

  * `isEmpty` : retourne `True` si la boîte est vide.
  * `contains` : compare l’élément avec le contenu de la boîte.
  * `replace` : remplace le contenu par un nouvel élément.
* `main` : teste les fonctions avec une boîte vide et une boîte remplie.

---

**Résultat à l’exécution**

```
emptyBox is empty? True
filledBox is empty? False
Does filledBox contain 42? True
Does filledBox contain 7? False
Replaced emptyBox with 99: Box (Just 99)
```

---
