## HC5T9 – Tâche 9 : Fonction d’ordre supérieur pour transformer une liste

###  Objectif

Créer une fonction `transformList` qui :

1. Prend une **fonction** `(a -> a)` et une **liste** `[a]` en entrée.
2. Applique la fonction **deux fois** à chaque élément de la liste.
3. Utilise **`map`** pour transformer chaque élément.
4. Peut fonctionner avec **n’importe quel type compatible** avec la fonction fournie.


###  Exemple corrigé avec `map` et fonction appliquée deux fois

```haskell
-- Fichier : Main.hs

-- Fonction qui applique une fonction deux fois à chaque élément d'une liste
transformList :: (a -> a) -> [a] -> [a]
transformList f = map (f . f)  -- compose f avec elle-même

-- Programme principal pour tester
main :: IO ()
main = do
    print $ transformList (+2) [1,2,3]    -- [5,6,7]   ((1+2)+2, (2+2)+2, (3+2)+2)
    print $ transformList (*3) [1,2,3]    -- [9,12,15] ((1*3)*3, (2*3)*3, (3*3)*3)
```

###  Explications

* `map (f . f)` = compose `f` avec elle-même et applique à chaque élément de la liste.
* `(f . f)` = équivalent à `\x -> f (f x)` mais en **style point-free**.
* Exemple : `(+2) . (+2)` appliqué à 1 → `(1+2)+2 = 5`.
* La fonction est **générique** et fonctionne pour n’importe quel type compatible avec la fonction donnée.


###  Résultats attendus

```
[5,6,7]
[9,12,15]
```
