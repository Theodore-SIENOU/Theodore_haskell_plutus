### **HC6T3 – Tâche 3 : Somme des éléments avec `foldr`**

#### **Sujet**

Implémente une fonction qui calcule la **somme des éléments d’une liste** en utilisant la fonction **`foldr`** (pliage à droite).

Rappel :
`foldr` a pour type général :

```haskell
foldr :: (a -> b -> b) -> b -> [a] -> b
```

Il prend :

* une fonction binaire,
* une valeur initiale,
* et une liste à parcourir de droite à gauche.

---

### **Correction complète**

```haskell
-- Fichier : Main.hs

-- Calcule la somme des éléments d'une liste en utilisant foldr
somme :: [Int] -> Int
somme = foldr (+) 0
-- foldr (+) 0 [1,2,3] = 1 + (2 + (3 + 0))

-- Fonction principale : test de la fonction somme
main :: IO ()
main = do
    let liste = [1, 2, 3, 4, 5]
    print ("Liste : " ++ show liste)
    print ("Somme des elements : " ++ show (somme liste))
```

---

### **Explication**

* **somme :: [Int] -> Int**
  → La fonction prend une liste d’entiers et retourne leur somme.

* **foldr (+) 0 [1,2,3,4,5]**
  → `foldr` applique `+` en partant de la droite :

  ```
  1 + (2 + (3 + (4 + (5 + 0))))
  = 15
  ```

* Le **0** est la valeur initiale (point de départ de la somme).

* L’opérateur **(+)** est appliqué à chaque élément de la liste.

* **main :: IO ()**
  → Sert à tester la fonction et afficher le résultat.

---

### **Résultat à l’exécution**

```
"Liste : [1,2,3,4,5]"
"Somme des elements : 15"
```

---
