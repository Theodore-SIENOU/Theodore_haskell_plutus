##  HC4T2 – Tâche 2 : carte d'identité électricé de télévision

###  Objectif

Créer une fonction `dayType :: String -> String` qui :

1. Prend en entrée le **nom d’un jour de la semaine** (`"Lundi"`, `"Mardi"`, …, `"Dimanche"`)
2. Retourne un message indiquant si c’est **un jour de semaine** ou **le week-end**
3. Si le jour est invalide, retourne `"Jour invalide"`



###  Exemple corrigé avec `case` et pattern matching

```haskell
-- Fichier : Main.hs

-- Fonction pour déterminer le type de jour
dayType :: String -> String
dayType jour = case jour of
    "Samedi"   -> "C'est le week-end"
    "Dimanche" -> "C'est le week-end"
    "Lundi"    -> "C'est un jour de semaine"
    "Mardi"    -> "C'est un jour de semaine"
    "Mercredi" -> "C'est un jour de semaine"
    "Jeudi"    -> "C'est un jour de semaine"
    "Vendredi" -> "C'est un jour de semaine"
    _          -> "Jour invalide"

-- Programme principal pour tester
main :: IO ()
main = do
    putStrLn $ dayType "Lundi"
    putStrLn $ dayType "Samedi"
    putStrLn $ dayType "Dimanche"
    putStrLn $ dayType "Funday"
```

###  Explications

* `case jour of` = permet de tester **tous les cas possibles**
* Chaque jour est un **pattern** qui retourne le message correspondant
* `_` = correspond à **tous les autres cas non définis** (jour invalide)


###  Résultats attendus

```
C'est un jour de semaine
C'est le week-end
C'est le week-end
Jour invalide
```
