### **HC10T9 – Classe de type MinMax**

**Sujet**
Implémenter une classe de type `MinMax` avec les méthodes :
`minValue :: a` et `maxValue :: a`,
et fournir une instance pour `Int`.

---

###  **Correction complète**

```haskell
-- Définition de la classe MinMax
class MinMax a where
    minValue :: a
    maxValue :: a

-- Instance pour le type Int
instance MinMax Int where
    minValue = minBound
    maxValue = maxBound

-- Fonction principale pour tester
main :: IO ()
main = do
    putStrLn $ "Valeur minimale (Int) : " ++ show (minValue :: Int)
    putStrLn $ "Valeur maximale (Int) : " ++ show (maxValue :: Int)
```

---

###  **Explication**

* La classe `MinMax` définit deux constantes :
  `minValue` et `maxValue`, représentant les bornes d’un type.
* Pour `Int`, on réutilise `minBound` et `maxBound`,
  qui sont disponibles grâce à la classe `Bounded`.

---

###  **Résultat attendu**

```
Valeur minimale (Int) : -9223372036854775808
Valeur maximale (Int) : 9223372036854775807
```

---
