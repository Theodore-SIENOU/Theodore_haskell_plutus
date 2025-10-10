### **HC6T2 – Tâche 2 : Suite de Fibonacci (récursif)**

#### **Sujet**

Implémente une **fonction récursive** qui calcule le **nième nombre de la suite de Fibonacci**.
Rappel de la définition mathématique :

* **F(0) = 0**
* **F(1) = 1**
* **F(n) = F(n−1) + F(n−2)** pour *n ≥ 2*

---

### **Correction complète**

```haskell
-- Fichier : Main.hs

-- Calcule le nième nombre de la suite de Fibonacci (version récursive)
fibonacci :: Int -> Int
fibonacci 0 = 0                         -- Cas de base : F(0) = 0
fibonacci 1 = 1                         -- Cas de base : F(1) = 1
fibonacci n = fibonacci (n - 1) + fibonacci (n - 2)  -- Cas récursif

-- Fonction principale : test de la fonction fibonacci
main :: IO ()
main = do
    let n = 10
    print ("Calcul du " ++ show n ++ "e nombre de Fibonacci")
    print ("Resultat : " ++ show (fibonacci n))
```

---

### **Explication**

* **fibonacci :: Int -> Int**
  → La fonction prend un entier `n` et retourne le *nième* nombre de Fibonacci.

* **Cas de base :**

  * `fibonacci 0 = 0`
  * `fibonacci 1 = 1`
    Ces deux cas empêchent la récursion de descendre indéfiniment.

* **Cas récursif :**
  `fibonacci n = fibonacci (n - 1) + fibonacci (n - 2)`
  La fonction s'appelle deux fois, une fois pour `n−1` et une autre pour `n−2`.

* **Exemple de calcul :**

  ```
  fibonacci 5 
  = fibonacci 4 + fibonacci 3
  = (fibonacci 3 + fibonacci 2) + (fibonacci 2 + fibonacci 1)
  = 3 + 2 = 5
  ```

* **main :: IO ()**
  → Point d’entrée du programme, où l’on teste la fonction avec `n = 10`.

---

### **Résultat à l’exécution**

```
"Calcul du 10e nombre de Fibonacci"
"Resultat : 55"
```

---
