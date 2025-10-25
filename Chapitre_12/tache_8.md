### **HC12T8 – Fusionner deux listes triées**

**Sujet :**
Définir une fonction `mergeLists` qui fusionne deux listes triées en une seule liste triée.
Utiliser la fonction `main` pour tester cette fonctionnalité.

---

###  **Correction complète**

```haskell
-- Fonction pour fusionner deux listes triées
mergeLists :: Ord a => [a] -> [a] -> [a]
mergeLists [] ys = ys
mergeLists xs [] = xs
mergeLists (x:xs) (y:ys)
    | x <= y    = x : mergeLists xs (y:ys)
    | otherwise = y : mergeLists (x:xs) ys

-- Fonction principale pour tester
main :: IO ()
main = do
    let list1 = [1, 3, 5, 7]
    let list2 = [2, 4, 6, 8, 10]
    let merged = mergeLists list1 list2
    putStrLn "Liste 1 :"
    print list1
    putStrLn "Liste 2 :"
    print list2
    putStrLn "Fusion des deux listes triées :"
    print merged
```

---

###  **Explication**

* La fonction `mergeLists` compare le **premier élément** de chaque liste :

  * Si `x <= y`, on place `x` d’abord et on continue avec le reste.
  * Sinon, on place `y`.
* Elle utilise la **récursion** jusqu’à ce qu’une des deux listes soit vide.
* La contrainte `Ord a` signifie que les éléments doivent être comparables (`<`, `<=`, etc.).

---

###  **Résultat attendu à l’exécution**

```
Liste 1 :
[1,3,5,7]
Liste 2 :
[2,4,6,8,10]
Fusion des deux listes triées :
[1,2,3,4,5,6,7,8,10]
```

---

###  **À retenir**

* Cette méthode est très proche de la **phase de fusion** dans l’algorithme **merge sort**.
* La fonction fonctionne avec **tous les types ordonnés** : nombres, caractères, etc.

  ```haskell
  mergeLists "ace" "bdf"   -- "abcdef"
  ```
