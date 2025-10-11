### **HC7T3 – Fonction avec contraintes multiples**

**Sujet :**
Écrire une fonction `compareValues` qui prend deux arguments de type `a` et retourne **le plus grand**.
 Le type `a` doit être une instance de **Eq** et **Ord**.

---

###  **Correction complète**

```haskell
-- Fonction compareValues avec contraintes Eq et Ord
compareValues :: (Eq a, Ord a) => a -> a -> a
compareValues x y
    | x >= y    = x
    | otherwise = y

-- Programme principal pour tester
main :: IO ()
main = do
    print (compareValues 10 20)     -- 20
    print (compareValues 5.5 3.2)   -- 5.5
    print (compareValues 'a' 'z')   -- 'z'
    print (compareValues "apple" "banana") -- "banana"
```

---

###  **Explication**

* `(Eq a, Ord a) =>` indique que le type `a` doit appartenir aux deux classes :

  * `Eq` → pour comparer l’égalité (`==`, `/=`).
  * `Ord` → pour comparer l’ordre (`<`, `>`, `<=`, `>=`).
* La fonction retourne le plus grand des deux éléments grâce à `>=`.

---

###  **Résultat attendu à l’exécution**

```
20
5.5
'z'
"banana"
```

---
