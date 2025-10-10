### **HC6T6 – Tâche 6 : Existence d’un élément dans une liste**

#### **Sujet**

Implémente une **fonction récursive** qui détermine si un **élément donné existe dans une liste**.
On ne doit pas utiliser la fonction prédéfinie `elem`, mais la recréer soi-même pour comprendre le principe.

---

### **Correction complète**

```haskell
-- Fichier : Main.hs

-- Vérifie récursivement si un élément existe dans une liste
existe :: (Eq a) => a -> [a] -> Bool
existe _ [] = False                        -- Cas de base : une liste vide ne contient aucun élément
existe x (y:ys)
    | x == y    = True                     -- Si l'élément courant est égal à x → trouvé !
    | otherwise = existe x ys              -- Sinon, on continue la recherche dans le reste de la liste

-- Fonction principale : test de la fonction existe
main :: IO ()
main = do
    let liste = [10, 20, 30, 40, 50]
    print ("Liste : " ++ show liste)
    print ("L'element 30 existe ? " ++ show (existe 30 liste))
    print ("L'element 99 existe ? " ++ show (existe 99 liste))
```

---

### **Explication**

* **existe :: (Eq a) => a -> [a] -> Bool**
  → La fonction prend :

  * un élément `x`
  * une liste `[a]`
  * et retourne un booléen `True` ou `False`.
    La contrainte `(Eq a)` indique que les éléments doivent être **comparables** (utilisation de `==`).

* **Cas de base : `existe _ [] = False`**
  → Si la liste est vide, aucun élément n’est trouvé.

* **Cas récursif :**
  On décompose la liste en :

  * `y` : premier élément
  * `ys` : reste de la liste
    Puis on compare :
  * Si `x == y`, on renvoie `True`.
  * Sinon, on continue la recherche avec `ys`.

* **main :: IO ()**
  → Sert à tester la fonction avec une liste `[10,20,30,40,50]`.

---

### **Résultat à l’exécution**

```
"Liste : [10,20,30,40,50]"
"L'element 30 existe ? True"
"L'element 99 existe ? False"
```

---
