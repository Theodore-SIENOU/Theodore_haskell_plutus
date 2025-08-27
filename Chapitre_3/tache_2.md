HC3T2 – Tâche 2 : Déterminer la note à partir d’un score**

###  Objectif

* Définir une fonction `grade` qui :

  * prend un `Int` représentant un score
  * retourne une **note** `"A"`, `"B"`, `"C"`, `"D"` ou `"F"`
  * utilise des **gardes (`|`)**

* Tester avec :

  * `grade 95`
  * `grade 72`
  * `grade 50`

---

###  Correction complète avec `main`

```haskell
-- Fichier : Main.hs

-- Détermine la note à partir du score
grade :: Int -> String
grade score
    | score >= 90 = "A"
    | score >= 80 = "B"
    | score >= 70 = "C"
    | score >= 60 = "D"
    | otherwise   = "F"

-- Fonction principale pour tester
main :: IO ()
main = do
    putStrLn $ "grade 95 = " ++ grade 95
    putStrLn $ "grade 72 = " ++ grade 72
    putStrLn $ "grade 50 = " ++ grade 50
```

---

###  Explication ligne par ligne

```haskell
grade :: Int -> String
```

* La fonction prend un entier (`Int`) et retourne une chaîne (`String`).

```haskell
grade score
    | score >= 90 = "A"
    | score >= 80 = "B"
    | score >= 70 = "C"
    | score >= 60 = "D"
    | otherwise   = "F"
```

* Les **gardes (`|`)** testent chaque condition dans l’ordre.
* `otherwise` est un raccourci pour `True`, c’est le **cas par défaut**.

```haskell
main = do ...
```

* Affiche le résultat de la fonction avec plusieurs valeurs de test.

---

###  Résultat attendu à l’exécution

```
grade 95 = A
grade 72 = C
grade 50 = F
