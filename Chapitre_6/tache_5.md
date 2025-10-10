### **HC6T5 – Tâche 5 : Inverser une liste (récursif)**

#### **Sujet**

Implémente une **fonction récursive** qui **inverse une liste** sans utiliser de fonctions prédéfinies comme `reverse`.

L’objectif est de comprendre comment manipuler les listes en **décomposant récursivement** leur structure.

---

### **Correction complète**

```haskell
-- Fichier : Main.hs

-- Inverse une liste de manière récursive
inverse :: [a] -> [a]
inverse [] = []                      -- Cas de base : la liste vide reste vide
inverse (x:xs) = inverse xs ++ [x]   -- Cas récursif : on inverse le reste et on ajoute x à la fin

-- Fonction principale : test de la fonction inverse
main :: IO ()
main = do
    let liste = [1, 2, 3, 4, 5]
    print ("Liste originale : " ++ show liste)
    print ("Liste inversee : " ++ show (inverse liste))
```

---

### **Explication**

* **inverse :: [a] -> [a]**
  → La fonction est polymorphe : elle fonctionne pour une liste d’éléments de n’importe quel type (`[a]`).

* **Cas de base : `inverse [] = []`**
  → Si la liste est vide, on renvoie une liste vide (rien à inverser).

* **Cas récursif : `inverse (x:xs) = inverse xs ++ [x]`**
  → On décompose la liste en :

  * `x` : le premier élément
  * `xs` : le reste de la liste
    On inverse récursivement `xs`, puis on ajoute `x` **à la fin** du résultat.

* **Exemple de calcul :**

  ```
  inverse [1,2,3]
  = inverse [2,3] ++ [1]
  = (inverse [3] ++ [2]) ++ [1]
  = ([] ++ [3] ++ [2]) ++ [1]
  = [3,2,1]
  ```

* **main :: IO ()**
  → Sert à tester la fonction avec une liste `[1,2,3,4,5]`.

---

### **Résultat à l’exécution**

```
"Liste originale : [1,2,3,4,5]"
"Liste inversee : [5,4,3,2,1]"
```

---
