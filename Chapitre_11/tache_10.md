**HC11T10 - Tâche 10 : Fonction `sortContainers`**

**Sujet**

Créer une fonction `sortContainers` qui prend une liste de containers (par exemple des `Box` ou tout type pour lequel `Ord` est défini) et les trie en utilisant l’instance `Ord` dérivée ou implémentée.

---

**Correction complète**

```haskell
-- Main.hs
import Data.List (sort)

-- Supposons que Box est défini ainsi avec Ord
data Box = Box Int deriving (Show, Eq, Ord)

-- Fonction qui trie une liste de containers
sortContainers :: Ord a => [a] -> [a]
sortContainers = sort

-- Fonction main pour tester
main :: IO ()
main = do
    let boxes = [Box 5, Box 2, Box 10, Box 1]
    print boxes
    print $ sortContainers boxes
```

---

**Explication**

* `import Data.List (sort)` : importe la fonction `sort` qui trie les listes selon l’instance `Ord`.
* `data Box = Box Int deriving (Show, Eq, Ord)` : exemple d’un container pour tester le tri.
* `sortContainers :: Ord a => [a] -> [a]` :

  * La fonction prend une liste de type `a` (doit être `Ord`) et retourne la liste triée.
  * La contrainte `Ord a` garantit que les éléments sont comparables.
* `sortContainers = sort` : simplement une utilisation directe de `sort`.

---

**Exemple de résultat à l’exécution**

```
[Box 5,Box 2,Box 10,Box 1]
[Box 1,Box 2,Box 5,Box 10]
```

---
