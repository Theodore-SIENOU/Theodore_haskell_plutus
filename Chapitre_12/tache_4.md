### **HC12T4 – Premiers 10 nombres de Fibonacci**

**Sujet :**
Écrire un programme qui calcule et affiche les **10 premiers nombres de Fibonacci** en utilisant la **récursion**.

---

###  **Correction complète**

```haskell
-- Définition de la fonction fibonacci
fibonacci :: Int -> Int
fibonacci 0 = 0
fibonacci 1 = 1
fibonacci n = fibonacci (n - 1) + fibonacci (n - 2)

-- Fonction principale
main :: IO ()
main = do
    let n = 10
    let fibs = [fibonacci i | i <- [0..n-1]]
    putStrLn "Les 10 premiers nombres de Fibonacci sont :"
    print fibs
```

---

###  **Explication**

* La **fonction `fibonacci`** est définie récursivement :

  * Cas de base :

    * `fibonacci 0 = 0`
    * `fibonacci 1 = 1`
  * Cas général :

    * `fibonacci n = fibonacci (n - 1) + fibonacci (n - 2)`
* `[fibonacci i | i <- [0..n-1]]` est une **liste en compréhension** qui calcule les 10 premiers termes.
* `print fibs` affiche la liste complète dans le terminal.

---

###  **Résultat attendu à l’exécution**

```
Les 10 premiers nombres de Fibonacci sont :
[0,1,1,2,3,5,8,13,21,34]
```

---
