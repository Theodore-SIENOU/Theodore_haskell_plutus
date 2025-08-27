## HC5T10 – Tâche 10 : Combiner les fonctions d’ordre supérieur

###  Objectif

Créer une fonction qui :

1. Prend en entrée une **liste de nombres**.
2. Calcule le **carré de chaque élément** (`map (^2)`).
3. Filtre pour ne garder que les **valeurs supérieures à 50** (`filter (>50)`).
4. Vérifie si **au moins un élément** satisfait cette condition (`any (>50)`).
5. Utilise la **composition et les fonctions d’ordre supérieur** pour combiner les étapes.


###  Exemple corrigé avec `map`, `filter` et `any`

```haskell
-- Fichier : Main.hs

-- Fonction qui vérifie si un carré est supérieur à 50
carreSuperieur50 :: [Int] -> Bool
carreSuperieur50 = any (>50) . map (^2)

-- Programme principal pour tester
main :: IO ()
main = do
    print $ carreSuperieur50 [1..5]    -- False
    print $ carreSuperieur50 [1..8]    -- True
    print $ carreSuperieur50 [10,2,3]  -- True
```

###  Explications

* `map (^2)` = calcule le **carré de chaque élément** de la liste.
* `any (>50)` = retourne `True` si **au moins un élément** satisfait la condition (>50).
* La composition `(any (>50) . map (^2))` = applique d’abord `map (^2)`, puis `any (>50)` sur le résultat.
* On pourrait ajouter `filter (>50)` mais ici `any (>50)` suffit, donc le `filter` est implicite dans `any`.


###  Résultats attendus

```
False
True
True
```
