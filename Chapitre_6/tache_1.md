### **HC6T1 – Tâche 1 : Factorielle (récursif)**

#### **Sujet**

Implémente une **fonction récursive** qui calcule la **factorielle** d’un nombre entier positif.
Rappel :

* **0! = 1**
* **n! = n × (n−1)!**

---

### **Correction complète**

```haskell
-- Fichier : Main.hs

-- Calcule la factorielle d’un nombre entier de manière récursive
factorielle :: Integer -> Integer
factorielle 0 = 1                      -- Cas de base : 0! = 1
factorielle n = n * factorielle (n - 1) -- Cas récursif : n! = n × (n−1)!

-- Fonction principale : test de la fonction factorielle
main :: IO ()
main = do
    let x = 5
    print ("Calcul de la factorielle de " ++ show x)
    print ("Resultat : " ++ show (factorielle x))
```

---

### **Explication**

* **factorielle :: Integer -> Integer**
  → La fonction prend un entier (`Integer`) et retourne un entier (`Integer`).

* **factorielle 0 = 1**
  → C’est le **cas de base** : sans cette condition, la récursion serait infinie.
  Quand `n = 0`, on arrête et renvoie 1.

* **factorielle n = n * factorielle (n - 1)**
  → C’est le **cas récursif** : la fonction s’appelle elle-même sur `n - 1`.
  Exemple :
  `factorielle 3 = 3 * factorielle 2 = 3 * 2 * factorielle 1 = 3 * 2 * 1 = 6`.

* **main :: IO ()**
  → Point d’entrée du programme.
  On choisit `x = 5` et on affiche le résultat dans le terminal.

---

### **Résultat à l’exécution**

```
"Calcul de la factorielle de 5"
"Resultat : 120"
```

---
