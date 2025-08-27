**HC3T9 – Tâche supérieure 9 : Trouver le maximum de trois nombres avec let**

###  Objectif

* Définir une fonction `maxOfThree` qui :

  * prend trois nombres `a`, `b`, `c` (`Int`)
  * utilise **let** pour stocker des valeurs intermédiaires
  * retourne le **maximum** des trois nombres

* Tester avec :

  * `maxOfThree 10 20 15`
  * `maxOfThree 5 25 10`

---

###  Correction complète avec `main`

```haskell
-- Fichier : Main.hs

-- Trouve le maximum de trois nombres
maxOfThree :: Int -> Int -> Int -> Int
maxOfThree a b c =
    let maxAB = if a > b then a else b
    in if maxAB > c then maxAB else c

-- Fonction principale pour tester
main :: IO ()
main = do
    putStrLn $ "maxOfThree 10 20 15 = " ++ show (maxOfThree 10 20 15)
    putStrLn $ "maxOfThree 5 25 10 = " ++ show (maxOfThree 5 25 10)
```

---

###  Explication ligne par ligne

```haskell
let maxAB = if a > b then a else b
```

* Compare `a` et `b` et stocke le **plus grand** dans `maxAB`.

```haskell
in if maxAB > c then maxAB else c
```

* Compare `maxAB` avec `c` pour obtenir le **maximum final**.

```haskell
main = do ...
```

* Affiche les résultats des tests avec `show` pour convertir les `Int` en `String`.

---

###  Résultat attendu à l’exécution

```
maxOfThree 10 20 15 = 20
maxOfThree 5 25 10 = 25
```
