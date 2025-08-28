##  HC4T7 – Tâche 7 : Ignorer des éléments dans une liste

###  Objectif

Créer une fonction `firstAndThird :: [a] -> [a]` qui :

1. Prend une **liste** en entrée.
2. Retourne **uniquement le premier et le troisième élément**.
3. Ignore tous les autres éléments de la liste.
4. Utilise le **pattern matching** pour extraire directement les éléments souhaités.


###  Exemple corrigé avec pattern matching

```haskell
-- Fichier : Main.hs

-- Fonction pour récupérer le premier et le troisième élément
firstAndThird :: [a] -> [a]
firstAndThird (x:_:z:_) = [x, z]
firstAndThird _         = []  -- Cas où la liste a moins de 3 éléments

-- Programme principal pour tester
main :: IO ()
main = do
    print $ firstAndThird [1,2,3,4,5]   -- [1,3]
    print $ firstAndThird ["a","b","c"] -- ["a","c"]
    print $ firstAndThird [1,2]         -- []
```


###  Explications

* `(x:_:z:_)` = pattern matching :

  * `x` = premier élément
  * `_` = **ignore le deuxième élément**
  * `z` = troisième élément
  * `_` = ignore tous les éléments restants
* `firstAndThird _ = []` = **cas générique** pour les listes de moins de 3 éléments
* La fonction retourne une **nouvelle liste** contenant uniquement les éléments désirés.


###  Résultats attendus

```
[1,3]
["a","c"]
[]
```
