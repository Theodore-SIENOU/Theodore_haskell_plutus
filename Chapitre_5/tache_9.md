**HC5T9 – Fonction d’ordre supérieur pour transformer une liste**

###  Énoncé

On veut écrire une fonction `transformList` qui prend une fonction `(a -> a)` et une liste `[a]`,
et applique **deux fois** cette fonction à chaque élément.


###  Solution Haskell

```haskell
-- applique deux fois f à chaque élément
transformList :: (a -> a) -> [a] -> [a]
transformList f xs = map (f . f) xs
```

###  Explication

* `map` applique une fonction à chaque élément d’une liste.
* `(f . f)` est la **composition de fonctions** : équivalent à `\x -> f (f x)`.
* Donc `map (f . f) xs` applique deux fois `f` à chaque élément de `xs`.


###  Exemple d’utilisation

```haskell
transformList (+1) [1,2,3]   -- Résultat : [3,4,5]
transformList (*2) [1,2,3]   -- Résultat : [4,8,12]
```
