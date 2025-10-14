### **HC10T2 – Classe de type `Summable`**

**Sujet :**
Créer une classe de type `Summable` qui fournit `sumUp :: [a] -> a`.
L’implémenter pour le type `Int`.

---

###  **Correction complète**

```haskell
-- Définition de la classe Summable
class Summable a where
    sumUp :: [a] -> a

-- Instance pour Int
instance Summable Int where
    sumUp = sum

-- Fonction principale pour tester
main :: IO ()
main = do
    let nums = [1, 2, 3, 4, 5] :: [Int]
    putStrLn $ "Somme de la liste : " ++ show (sumUp nums)
```

---

###  **Explication**

* `class Summable a` définit une interface pour tous les types qui peuvent être sommés.
* `sumUp` prend une liste d’éléments et retourne leur somme.
* L’instance pour `Int` utilise simplement la fonction `sum` prédéfinie.
* La liste `nums` est annotée `:: [Int]` pour éviter les ambiguïtés de type lors de la compilation.

---

###  **Résultat attendu à l’exécution**

```
Somme de la liste : 15
```

---
