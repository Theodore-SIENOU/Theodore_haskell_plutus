**HC5T7 – L’opérateur `$`**.

### Objectif

 Réécrire la fonction suivante en utilisant l’opérateur $ :
 result = sum (map (*2) (filter (>3) [1..10]))


###  Version initiale

```haskell
result = sum (map (*2) (filter (>3) [1..10]))
```

###  Avec `$`

```haskell
result = sum $ map (*2) $ filter (>3) [1..10]
```

###  Explication

* L’opérateur `$` a le type :

  ```haskell
  ($) :: (a -> b) -> a -> b
  ```
* Il permet d’**éviter les parenthèses** car :

  ```haskell
  f $ g x  ≡  f (g x)
  ```
* Ici, on lit de droite à gauche :

  1. `filter (>3) [1..10]` garde les nombres > 3.
  2. `map (*2)` multiplie chaque élément par 2.
  3. `sum` fait la somme.
