### **HC10T8 – Sous-classe AdvancedEq de Eq**

**Sujet**
Définir une sous-classe `AdvancedEq` de `Eq` avec une méthode supplémentaire
`compareEquality :: a -> a -> Bool`.

---

###  **Correction complète**

```haskell
-- Définition de la sous-classe AdvancedEq
class Eq a => AdvancedEq a where
    compareEquality :: a -> a -> Bool

-- Instance pour le type Int
instance AdvancedEq Int where
    compareEquality x y = x == y

-- Fonction principale pour tester
main :: IO ()
main = do
    print (compareEquality (5 :: Int) (5 :: Int))   -- True
    print (compareEquality (5 :: Int) (10 :: Int))  -- False
```

---

###  **Explication**

* `(5 :: Int)` indique explicitement que `5` est de type `Int`.
  Cela supprime toute ambiguïté sur le type.
* `class Eq a => AdvancedEq a` fait de `AdvancedEq` une **sous-classe** de `Eq`.
* L’instance `AdvancedEq Int` définit la logique pour `Int` en utilisant `==`.

---

###  **Résultat attendu**

```
True
False
```

---
