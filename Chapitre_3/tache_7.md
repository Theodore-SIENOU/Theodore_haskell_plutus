HC3T7 – Tâche avancée 7 : Déterminer la saison selon le mois

###  Objectif

* Définir une fonction `season` qui :

  * prend un **mois** (`Int`)
  * retourne la **saison** correspondante (`String`)
  * utilise des **gardes (`|`)**

* Tester avec :

  * `season 3` → Printemps
  * `season 7` → Été
  * `season 11` → Automne

---

###  Correction complète avec `main`

```haskell
-- Fichier : Main.hs

-- Détermine la saison selon le mois
season :: Int -> String
season month
    | month == 12 || month == 1 || month == 2 = "Hiver"
    | month >= 3 && month <= 5 = "Printemps"
    | month >= 6 && month <= 8 = "Été"
    | month >= 9 && month <= 11 = "Automne"
    | otherwise = "Mois invalide"

-- Fonction principale pour tester
main :: IO ()
main = do
    putStrLn $ "season 3 = " ++ season 3
    putStrLn $ "season 7 = " ++ season 7
    putStrLn $ "season 11 = " ++ season 11
```

---

###  Explication ligne par ligne

```haskell
season month
    | month == 12 || month == 1 || month == 2 = "Hiver"
```

* Si le mois est décembre, janvier ou février → Hiver.

```haskell
    | month >= 3 && month <= 5 = "Printemps"
```

* Mois 3 à 5 → Printemps.

```haskell
    | month >= 6 && month <= 8 = "Été"
```

* Mois 6 à 8 → Été.

```haskell
    | month >= 9 && month <= 11 = "Automne"
```

* Mois 9 à 11 → Automne.

```haskell
    | otherwise = "Mois invalide"
```

* Pour gérer les entrées hors 1–12.

---

###  Résultat attendu à l’exécution

```
season 3 = Printemps
season 7 = Été
season 11 = Automne
