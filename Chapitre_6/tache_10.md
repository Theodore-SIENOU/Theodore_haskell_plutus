### **HC6T10 – Tâche 10 : Récupérer les chiffres d’un nombre**

#### **Sujet**

Implémente une **fonction récursive** qui prend un entier `n` et retourne **une liste contenant chacun de ses chiffres**.
Exemple : pour `12345`, le résultat doit être `[1,2,3,4,5]`.

---

### **Correction complète**

```haskell
-- Fichier : Main.hs

-- Récupère les chiffres d'un nombre
digits :: Int -> [Int]
digits n
    | n < 10    = [n]               -- Cas de base : un seul chiffre
    | otherwise = digits (n `div` 10) ++ [n `mod` 10]  -- Récursif : séparer le dernier chiffre

-- Fonction principale : test de digits
main :: IO ()
main = do
    let nombre = 12345
    print ("Nombre : " ++ show nombre)
    print ("Chiffres : " ++ show (digits nombre))
```

---

### **Explication**

* **digits :: Int -> [Int]**
  → La fonction prend un entier et retourne la liste de ses chiffres.

* **Cas de base : `n < 10`**
  → Si le nombre est inférieur à 10, c’est un chiffre unique → on retourne `[n]`.

* **Cas récursif : `digits (n `div`10) ++ [n`mod` 10]`**
  → `n div 10` → enlève le dernier chiffre et continue récursivement.
  → `n mod 10` → récupère le dernier chiffre et l’ajoute à la fin de la liste.

* **main :: IO ()**
  → Sert à tester la fonction avec un exemple concret (`12345`).

---

### **Résultat à l’exécution**

```
"Nombre : 12345"
"Chiffres : [1,2,3,4,5]"
```

---
