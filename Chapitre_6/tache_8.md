### **HC6T8 – Tâche 8 : Filtrer les nombres pairs**

#### **Sujet**

Implémente une **fonction récursive** qui prend une liste de nombres et retourne **une liste ne contenant que les nombres pairs**.
Le but est de comprendre la récursion et l’utilisation de conditions (`if` ou gardes) pour filtrer des éléments.

---

### **Correction complète**

```haskell
-- Fichier : Main.hs

-- Filtre les nombres pairs d'une liste
pairs :: [Int] -> [Int]
pairs [] = []                              -- Cas de base : une liste vide retourne une liste vide
pairs (x:xs)
    | even x    = x : pairs xs             -- Si x est pair, on le garde et on continue avec xs
    | otherwise = pairs xs                  -- Sinon, on ignore x et on continue avec xs

-- Fonction principale : test de la fonction pairs
main :: IO ()
main = do
    let liste = [1,2,3,4,5,6,7,8,9,10]
    print ("Liste : " ++ show liste)
    print ("Nombres pairs : " ++ show (pairs liste))
```

---

### **Explication**

* **pairs :: [Int] -> [Int]**
  → La fonction prend une liste d’entiers `[Int]` et retourne une liste contenant uniquement les nombres pairs.

* **Cas de base : `pairs [] = []`**
  → Une liste vide n’a pas d’éléments, donc le résultat est vide.

* **Cas récursif avec gardes :**

  * **`even x`** → Vérifie si `x` est pair.
    → Si vrai, on inclut `x` dans le résultat (`x : pairs xs`).
    → Sinon, on continue avec le reste de la liste (`pairs xs`).

* **main :: IO ()**
  → Sert à tester la fonction avec une liste `[1..10]`.

---

### **Résultat à l’exécution**

```
"Liste : [1,2,3,4,5,6,7,8,9,10]"
"Nombres pairs : [2,4,6,8,10]"
```

---
