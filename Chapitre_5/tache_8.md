##  HC5T8 – Tâche 8 : Style point-free

###  Objectif

 Convertir la fonction suivante en style point-free :
 addFive x = x + 5

```haskell
addFive x = x + 5
```

Donc :

1. Transformer cette définition en une version équivalente **sans `x`**.
2. Utiliser la **partially applied function** `(+) 5`.


###  Exemple corrigé en style point-free

```haskell
-- Fichier : Main.hs

-- Version point-free
addFive :: Int -> Int
addFive = (+ 5)

-- Programme principal pour tester
main :: IO ()
main = do
    print $ addFive 0     -- 5
    print $ addFive 10    -- 15
    print $ addFive (-3)  -- 2
```

###  Explications

* `addFive x = x + 5` → prend un nombre et ajoute 5.
* `(+ 5)` = une fonction qui attend un argument, et ajoute 5 à ce dernier.
* En écrivant `addFive = (+ 5)`, on supprime l’argument `x` → c’est le **style point-free**.
* Le type reste `Int -> Int`.


###  Résultats attendus

```
5
15
2
```
