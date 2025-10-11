### **HC7T10 – Fonction avec plusieurs contraintes de classes de types**

**Sujet :**
Écrire une fonction `describeAndCompare` qui prend deux valeurs `Describable` et retourne la description de la plus grande.
Les valeurs doivent être à la fois `Describable` et `Ord`.

---

###  **Correction complète**

```haskell
-- Définition de la classe Describable
class Describable a where
    describe :: a -> String

-- Instances pour Int et Bool
instance Describable Int where
    describe n = "The number is " ++ show n

instance Describable Bool where
    describe True  = "It is True"
    describe False = "It is False"

-- Fonction describeAndCompare
describeAndCompare :: (Describable a, Ord a) => a -> a -> String
describeAndCompare x y =
    if x >= y then describe x else describe y

-- Fonction principale pour tester
main :: IO ()
main = do
    print $ describeAndCompare (10 :: Int) (5 :: Int)   -- "The number is 10"
    print $ describeAndCompare (3 :: Int) (7 :: Int)    -- "The number is 7"
    print $ describeAndCompare True False               -- "It is True"
    print $ describeAndCompare False True               -- "It is True"
```

---

###  **Explication**

* La classe `Describable` fournit une méthode `describe` pour transformer une valeur en chaîne de caractères.
* La fonction `describeAndCompare` nécessite que les deux valeurs soient `Describable` **et** `Ord` pour pouvoir comparer (`>=`) et ensuite décrire la plus grande valeur.
* Les annotations de type comme `(10 :: Int)` ou `(3 :: Int)` sont importantes pour éviter les ambiguïtés lors de la compilation.

---

###  **Résultat attendu à l’exécution**

```
"The number is 10"
"The number is 7"
"It is True"
"It is True"
```

---
