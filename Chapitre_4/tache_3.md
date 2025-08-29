**HC4T3 – Tâche 3 : un écran d'avertissement de système**.

## Sujet


    Écrire une fonction gradeComment :: Int -> String qui prend une note et retourne un commentaire selon la tranche :
        90 - 100 → « Excellent ! »
        70 - 89 → « Bon travail ! »
        50 - 69 → « Tu as réussi. »
        0 - 49 → « Peut mieux faire. »
        Tout autre nombre → « Note invalide. »


##  Correction avec gardes (`|`)

```haskell
-- Fichier : Main.hs

-- Fonction qui donne un commentaire en fonction d'une note
gradeComment :: Int -> String
gradeComment note
    | note >= 90 && note <= 100 = "Excellent"
    | note >= 70 && note <= 89  = "Bon travail"
    | note >= 50 && note <= 69  = "Tu as réussi."
    | note >= 0  && note <= 49  = "Peut mieux faire."
    | otherwise                 = "Note invalide"

-- Programme principal pour tester
main :: IO ()
main = do
    putStrLn $ "gradeComment 95 = " ++ gradeComment 95
    putStrLn $ "gradeComment 75 = " ++ gradeComment 75
    putStrLn $ "gradeComment 60 = " ++ gradeComment 60
    putStrLn $ "gradeComment 30 = " ++ gradeComment 30
    putStrLn $ "gradeComment 120 = " ++ gradeComment 120
```

##  Explications

* `|` = garde (permet de vérifier plusieurs conditions en cascade).
* `otherwise` = cas par défaut (équivaut à `True`).
* Chaque intervalle correspond à une tranche de notes.


##  Résultats attendus

```
gradeComment 95 = Excellent
gradeComment 75 = Bon travail
gradeComment 60 = Tu as réussi.
gradeComment 30 = Peut mieux faire.
gradeComment 120 = Note invalide
```
