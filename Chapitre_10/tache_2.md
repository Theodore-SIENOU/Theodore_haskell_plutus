### **HC10T2 - Classe de type Summable**

**Sujet**

* Créer une classe de type `Summable` qui fournit la fonction `sumUp :: [a] -> a`.
* Implémenter cette classe pour le type `Int`.
* Tester la fonction avec une liste d’entiers `[1,2,3,4,5]`.

---

**Correction complète**

```haskell
-- Fichier : Main.hs

-- Définition de la classe de type Summable
class Summable a where
    sumUp :: [a] -> a

-- Instance de Summable pour Int
instance Summable Int where
    sumUp = foldr (+) 0

-- Fonction principale pour tester
main :: IO ()
main = do
    let nums :: [Int]         -- Annotation de type nécessaire pour éviter l'ambiguïté
        nums = [1, 2, 3, 4, 5]
    putStrLn $ "Somme de la liste : " ++ show (sumUp nums)
```

---

**Explication**

* `class Summable a where sumUp :: [a] -> a` : définit une classe de type paramétrique qui peut sommer des listes d’éléments de type `a`.
* `instance Summable Int` : implémente `sumUp` pour les `Int` en utilisant `foldr (+) 0` pour sommer tous les éléments de la liste.
* `let nums :: [Int]` : l’annotation de type est obligatoire ici pour résoudre l’ambiguïté de type.
* `putStrLn $ "Somme de la liste : " ++ show (sumUp nums)` : affiche le résultat de la somme de la liste converti en chaîne de caractères grâce à `show`.

---

**Résultat à l’exécution**

```
Somme de la liste : 15
```

---
