### **HC6T9 – Tâche 9 : Implémentation de map**

#### **Sujet**

Implémente une **fonction récursive** qui prend une fonction et une liste, puis retourne **une nouvelle liste avec la fonction appliquée à chaque élément**.
C’est l’équivalent de la fonction `map` intégrée en Haskell.

---

### **Correction complète**

```haskell
-- Fichier : Main.hs

-- Applique une fonction à chaque élément d'une liste
map' :: (a -> b) -> [a] -> [b]
map' _ [] = []                        -- Cas de base : appliquer une fonction à une liste vide donne une liste vide
map' f (x:xs) = f x : map' f xs       -- Cas récursif : appliquer f à x et continuer avec xs

-- Fonction principale : test de map'
main :: IO ()
main = do
    let liste = [1,2,3,4,5]
    print ("Liste originale : " ++ show liste)
    print ("Chaque élément multiplié par 2 : " ++ show (map' (*2) liste))
    print ("Chaque élément incrémenté de 1 : " ++ show (map' (+1) liste))
```

---

### **Explication**

* **map' :: (a -> b) -> [a] -> [b]**
  → La fonction prend :

  1. Une fonction `f` qui transforme un type `a` en un type `b`.
  2. Une liste `[a]`.
     → Retourne une nouvelle liste `[b]` contenant chaque élément transformé par `f`.

* **Cas de base : `map' _ [] = []`**
  → Si la liste est vide, le résultat est une liste vide.

* **Cas récursif : `map' f (x:xs) = f x : map' f xs`**
  → On applique `f` au premier élément `x` et on concatène le résultat avec l’appel récursif sur le reste de la liste `xs`.

* **main :: IO ()**
  → Sert à tester la fonction avec deux transformations différentes (`(*2)` et `(+1)`).

---

### **Résultat à l’exécution**

```
"Liste originale : [1,2,3,4,5]"
"Chaque élément multiplié par 2 : [2,4,6,8,10]"
"Chaque élément incrémenté de 1 : [2,3,4,5,6]"
```

---
