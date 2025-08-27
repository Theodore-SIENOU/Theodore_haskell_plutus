**HC3T5 – Tâche 5 : Déterminer le type d'un triangle avec des gardes**

###  Objectif

* Définir une fonction `triangleType` qui :

  * prend trois côtés `a`, `b`, `c` (type `Int` ou `Float`)
  * retourne :

    * `"Équilatéral"` si tous les côtés sont égaux
    * `"Isocèle"` si exactement deux côtés sont égaux
    * `"Scalène"` si aucun côté n’est égal
  * utilise des **gardes (`|`)**

* Tester avec :

  * `triangleType 3 3 3`
  * `triangleType 5 5 8`
  * `triangleType 6 7 8`

###  Correction complète avec `main`

```haskell
-- Fichier : Main.hs

-- Détermine le type d'un triangle
triangleType :: (Eq a) => a -> a -> a -> String
triangleType a b c
    | a == b && b == c = "Équilatéral"
    | a == b || a == c || b == c = "Isocèle"
    | otherwise = "Scalène"

-- Fonction principale pour tester
main :: IO ()
main = do
    putStrLn $ "triangleType 3 3 3 = " ++ triangleType 3 3 3
    putStrLn $ "triangleType 5 5 8 = " ++ triangleType 5 5 8
    putStrLn $ "triangleType 6 7 8 = " ++ triangleType 6 7 8
```

###  Explication ligne par ligne

```haskell
triangleType :: (Eq a) => a -> a -> a -> String
```

* `Eq a` : le type doit pouvoir être **comparé avec `==`**.
* La fonction prend trois valeurs `a` et retourne une chaîne.

```haskell
| a == b && b == c = "Équilatéral"
```

* Tous les côtés sont égaux → triangle équilatéral.

```haskell
| a == b || a == c || b == c = "Isocèle"
```

* Deux côtés au moins égaux → triangle isocèle.

```haskell
| otherwise = "Scalène"
```

* Aucun côté égal → triangle scalène.

### Résultat attendu à l’exécution

```
triangleType 3 3 3 = Équilatéral
triangleType 5 5 8 = Isocèle
triangleType 6 7 8 = Scalène
