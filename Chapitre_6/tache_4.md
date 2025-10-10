### **HC6T4 – Tâche 4 : Produit des éléments avec `foldl`**

#### **Sujet**

Implémente une fonction qui calcule le **produit des éléments d’une liste** en utilisant la fonction **`foldl`** (pliage à gauche).

Rappel :
`foldl` a pour type général :

```haskell
foldl :: (b -> a -> b) -> b -> [a] -> b
```

Il applique une fonction en parcourant la liste **de gauche à droite**.

---

### **Correction complète**

```haskell
-- Fichier : Main.hs

-- Calcule le produit des éléments d'une liste en utilisant foldl
produit :: [Int] -> Int
produit = foldl (*) 1
-- foldl (*) 1 [1,2,3,4] = (((1 * 1) * 2) * 3) * 4

-- Fonction principale : test de la fonction produit
main :: IO ()
main = do
    let liste = [1, 2, 3, 4, 5]
    print ("Liste : " ++ show liste)
    print ("Produit des elements : " ++ show (produit liste))
```

---

### **Explication**

* **produit :: [Int] -> Int**
  → La fonction prend une liste d’entiers et retourne le produit de tous ses éléments.

* **foldl (*) 1 [1,2,3,4,5]**
  → `foldl` parcourt la liste de **gauche à droite**, en accumulant le résultat :

  ```
  (((((1 * 1) * 2) * 3) * 4) * 5)
  = 120
  ```

* Le **1** est la valeur initiale (neutre pour la multiplication).

* L’opérateur **(*)** est appliqué à chaque élément successivement.

* **main :: IO ()**
  → Sert à tester la fonction avec une liste `[1,2,3,4,5]` et à afficher le résultat.

---

### **Résultat à l’exécution**

```
"Liste : [1,2,3,4,5]"
"Produit des elements : 120"
```

---
