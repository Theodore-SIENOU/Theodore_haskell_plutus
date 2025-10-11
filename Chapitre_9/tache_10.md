### **HC9T10 - Tâche 10 : Type d’arbre binaire de recherche (BST)**

#### **Sujet**

> Définir un type d’arbre binaire de recherche `BST a` avec des constructeurs pour un arbre vide et un nœud contenant une valeur et deux sous-arbres.

---

###  **Correction complète**

```haskell
-- Fichier : Main.hs

-- Définition du type BST (Binary Search Tree)
data BST a = Empty
           | Node a (BST a) (BST a)
           deriving (Show, Eq)

-- Exemple d'arbre BST
bstExample :: BST Int
bstExample = Node 10
                (Node 5 Empty Empty)
                (Node 15 (Node 12 Empty Empty) Empty)

main :: IO ()
main = do
    putStrLn "Exemple de BST :"
    print bstExample
```

---

###  **Explication**

* `BST a` est un type récursif :

  * `Empty` représente un arbre vide.
  * `Node a (BST a) (BST a)` représente un nœud avec :

    * une valeur `a`,
    * un sous-arbre gauche,
    * un sous-arbre droit.
* `deriving (Show, Eq)` permet d’afficher l’arbre et de le comparer facilement.
* `bstExample` montre un exemple d’arbre avec racine `10`, gauche `5`, droite `15` (qui a lui-même un enfant `12`).

---

### **Résultat à l’exécution**

```
Exemple de BST :
Node 10 (Node 5 Empty Empty) (Node 15 (Node 12 Empty Empty) Empty)
```

---
