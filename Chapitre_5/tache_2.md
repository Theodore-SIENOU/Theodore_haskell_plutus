##  HC5T2 – Tâche 2 : Filtrer les nombres impairs

###  Objectif

Créer une fonction qui :

1. Utilise `filter` pour extraire uniquement les **nombres impairs** d’une liste d’entiers.
2. Prend comme exemple la liste `[1..30]`.
3. Retourne une nouvelle liste contenant seulement les impairs.


###  Exemple corrigé avec `filter`

```haskell
-- Fichier : Main.hs

-- Fonction pour filtrer les nombres impairs
nombresImpairs :: [Int] -> [Int]
nombresImpairs xs = filter odd xs

-- Programme principal pour tester
main :: IO ()
main = do
    let liste = [1..30]
    print $ nombresImpairs liste
```

---

###  Explications

* `filter` = prend une fonction et une liste, et garde seulement les éléments qui **satisfont la condition**.
* `odd` = prédicat qui retourne `True` si un nombre est **impair**.
* `[1..30]` = notation pour générer la liste de tous les entiers de 1 à 30.
* `print` = affiche la liste des nombres impairs résultants.

###  Résultats attendus

```
[1,3,5,7,9,11,13,15,17,19,21,23,25,27,29]
```
