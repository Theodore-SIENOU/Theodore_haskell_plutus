### **HC6T7 – Tâche 7 : Taille d’une liste**

#### **Sujet**

Implémente une **fonction récursive** qui prend une liste et retourne sa **longueur** (le nombre d’éléments qu’elle contient).
Le but est de comprendre comment parcourir récursivement une liste sans utiliser la fonction prédéfinie `length`.

---

### **Correction complète**

```haskell
-- Fichier : Main.hs

-- Calcule la taille (longueur) d'une liste de manière récursive
taille :: [a] -> Int
taille [] = 0                     -- Cas de base : une liste vide a une taille de 0
taille (_:xs) = 1 + taille xs     -- Cas récursif : on ignore le premier élément et on compte le reste

-- Fonction principale : test de la fonction taille
main :: IO ()
main = do
    let liste = ["Haskell", "est", "amusant"]
    print ("Liste : " ++ show liste)
    print ("Taille de la liste : " ++ show (taille liste))
```

---

### **Explication**

* **taille :: [a] -> Int**
  → La fonction prend une liste d’éléments de n’importe quel type `[a]` et retourne un entier `Int` représentant sa longueur.

* **Cas de base : `taille [] = 0`**
  → Si la liste est vide, il n’y a rien à compter.

* **Cas récursif : `taille (_:xs) = 1 + taille xs`**
  → On ignore le premier élément (`_`) et on compte récursivement le reste de la liste `xs`.
  Exemple :

  ```
  taille [10,20,30]
  = 1 + taille [20,30]
  = 1 + (1 + taille [30])
  = 1 + (1 + (1 + taille []))
  = 3
  ```

* **main :: IO ()**
  → Permet de tester la fonction avec une liste de chaînes de caractères.

---

### **Résultat à l’exécution**

```
"Liste : [\"Haskell\",\"est\",\"amusant\"]"
"Taille de la liste : 3"
```

---
