##  HC5T4 – Tâche 4 : Utiliser les fonctions lambda

###  Objectif

Réécrire la fonction suivante en utilisant une **fonction lambda** :

```haskell
biggerThan10 x = x > 10
```

Donc :

1. Transformer cette fonction classique en une version équivalente avec une **lambda** (`\x -> ...`).
2. Tester le comportement avec plusieurs valeurs.

---

###  Exemple corrigé avec lambda

```haskell
-- Fichier : Main.hs

-- Définition avec une fonction lambda
biggerThan10 :: Int -> Bool
biggerThan10 = \x -> x > 10

-- Programme principal pour tester
main :: IO ()
main = do
    print $ biggerThan10 5    -- False
    print $ biggerThan10 10   -- False
    print $ biggerThan10 15   -- True
```

###  Explications

* `\x -> x > 10` = syntaxe d’une **fonction anonyme (lambda)** qui prend `x` et retourne `True` si `x > 10`.
* On écrit `biggerThan10 = \x -> x > 10` au lieu de `biggerThan10 x = x > 10`.
* La fonction garde le même type : `Int -> Bool`.
* Les appels `biggerThan10 5` ou `biggerThan10 15` fonctionnent exactement de la même manière.


###  Résultats attendus

```
False
False
True
```
