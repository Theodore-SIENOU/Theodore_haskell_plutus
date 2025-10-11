### **HC9T8 - Tâche 8 : Type récursif Sequence**

#### **Sujet**

> Définir un type de données récursif `Sequence a` représentant une séquence linéaire de nœuds, chacun contenant une valeur et pointant vers le nœud suivant.

---

###  **Correction complète**

```haskell
-- Fichier : Main.hs

-- Définition du type récursif Sequence
data Sequence a = Node a (Sequence a) | Empty
    deriving (Show, Eq)

-- Exemple de séquence
seq1 :: Sequence Int
seq1 = Node 1 (Node 2 (Node 3 Empty))

-- Fonction pour afficher les éléments de la séquence sous forme de liste
toList :: Sequence a -> [a]
toList Empty        = []
toList (Node x xs)  = x : toList xs

main :: IO ()
main = do
    print seq1
    putStrLn ("Séquence sous forme de liste : " ++ show (toList seq1))
```

---

###  **Explication**

* `Sequence a` est un type **paramétrique et récursif** :

  * `Node a (Sequence a)` → contient une valeur `a` et un pointeur vers le **nœud suivant**
  * `Empty` → marque la **fin de la séquence**
* La fonction `toList` permet de **convertir la séquence en liste Haskell classique** pour un affichage facile :

  * Si la séquence est `Empty`, retourne une liste vide
  * Sinon, ajoute la valeur du nœud courant en tête (`:`) et continue récursivement

---

### **Résultat à l’exécution**

```
Node 1 (Node 2 (Node 3 Empty))
Séquence sous forme de liste : [1,2,3]
```

---
