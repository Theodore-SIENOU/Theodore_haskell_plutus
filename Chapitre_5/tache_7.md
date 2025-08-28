## HC5T7 – Tâche 7 : Utiliser l’opérateur `$`

###  Objectif

Réécrire l’expression suivante en utilisant l’**opérateur `$`** pour simplifier les parenthèses :

```haskell
result = sum (map (*2) (filter (>3) [1..10]))
```

1. `$` permet de **remplacer les parenthèses extérieures** et rendre le code plus lisible.
2. Conserver exactement le même calcul : filtrer les nombres supérieurs à 3, doubler chacun et faire la somme.

---

### Exemple corrigé avec `$`

```haskell
-- Fichier : Main.hs

-- Version avec l'opérateur $
result :: Int
result = sum $ map (*2) $ filter (>3) [1..10]

-- Programme principal pour tester
main :: IO ()
main = do
    print result
```


###  Explications

* `$` = permet d’éviter les parenthèses, tout ce qui est à droite de `$` est considéré comme **argument de la fonction** à gauche.
* `sum $ map (*2) $ filter (>3) [1..10]` équivaut à `sum (map (*2) (filter (>3) [1..10]))`.
* Les étapes :

  1. `filter (>3) [1..10]` → `[4,5,6,7,8,9,10]`
  2. `map (*2)` → `[8,10,12,14,16,18,20]`
  3. `sum` → `98`

###  Résultats attendus

```
98
```
