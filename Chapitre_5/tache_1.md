##  HC5T1 – Tâche 1 : Utiliser `applyTwice`

###  Objectif

Créer une fonction qui :

1. Prend une **fonction** `(Int -> Int)` et un **entier** en entrée.
2. Applique la fonction **trois fois** à l’entier.
3. Utilise éventuellement une fonction auxiliaire `applyTwice` (qui applique une fonction deux fois).


### Exemple corrigé avec `applyTwice`

```haskell
-- Fichier : Main.hs

-- Fonction qui applique une fonction deux fois
applyTwice :: (a -> a) -> a -> a
applyTwice f x = f (f x)

-- Fonction qui applique une fonction trois fois
applyThrice :: (a -> a) -> a -> a
applyThrice f x = f (applyTwice f x)

-- Programme principal pour tester
main :: IO ()
main = do
    print $ applyThrice (+2) 5    -- 11  (5+2=7, 7+2=9, 9+2=11)
    print $ applyThrice (*3) 2    -- 54  (2*3=6, 6*3=18, 18*3=54)
```


###  Explications

* `applyTwice f x = f (f x)` = applique `f` **deux fois** à `x`.
* `applyThrice f x = f (applyTwice f x)` = applique `f` **une troisième fois** sur le résultat de `applyTwice`.
* `(+) 2` ou `(*3)` = exemples de fonctions passées en argument.
* `applyThrice` peut fonctionner avec **toutes les fonctions de type `a -> a`**, pas seulement `Int -> Int`.


###  Résultats attendus

```
11
54
```
