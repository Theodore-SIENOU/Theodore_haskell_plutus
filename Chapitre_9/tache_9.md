### **HC9T9 - Tâche 9 : Vérifier la présence d’un élément dans une Sequence**

#### **Sujet**

> Créer une fonction `elemSeq` qui vérifie si un élément donné est présent dans une `Sequence`.

---

### **Correction complète**

```haskell
-- Fichier : Main.hs

-- Définition du type récursif Sequence
data Sequence a = Node a (Sequence a) | Empty
    deriving (Show, Eq)

-- Fonction pour vérifier la présence d'un élément
elemSeq :: Eq a => a -> Sequence a -> Bool
elemSeq _ Empty        = False
elemSeq item (Node x xs)
    | item == x        = True
    | otherwise        = elemSeq item xs

-- Exemple de séquence
seq1 :: Sequence Int
seq1 = Node 1 (Node 2 (Node 3 Empty))

main :: IO ()
main = do
    print seq1
    putStrLn ("2 est dans la séquence ? " ++ show (elemSeq 2 seq1))
    putStrLn ("5 est dans la séquence ? " ++ show (elemSeq 5 seq1))
```

---

###  **Explication**

* La fonction `elemSeq` prend un élément `item` et une `Sequence` :

  * Si la séquence est `Empty`, l’élément n’est pas présent → `False`.
  * Si le nœud courant `x` est égal à `item` → `True`.
  * Sinon, on continue la recherche récursivement dans le reste de la séquence.
* `Eq a =>` est nécessaire pour pouvoir comparer les éléments avec `==`.

---

### **Résultat à l’exécution**

```
Node 1 (Node 2 (Node 3 Empty))
2 est dans la séquence ? True
5 est dans la séquence ? False
```

---
