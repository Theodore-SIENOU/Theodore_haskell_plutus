##  HC4T5 – Tâche 5 : Ajouter un cas générique avec un message personnalisé

###  Objectif

Modifier la fonction `specialBirthday :: Int -> String` (de HC4T4) pour :

1. Retourner un **message spécial** pour certains âges précis :

   * `1` → `"Joyeux premier anniversaire !"`
   * `18` → `"Félicitations pour tes 18 ans !"`
   * `60` → `"Joyeux anniversaire pour tes 60 ans !"`
2. Pour **tous les autres âges**, inclure l’âge dans le message générique, par exemple : `"Joyeux anniversaire pour tes 25 ans !"`
3. Utiliser le **pattern matching** avec un cas générique (`_`) pour gérer les autres âges.



###  Exemple corrigé avec `case` et cas générique

```haskell
-- Fichier : Main.hs

-- Fonction anniversaire spéciale avec message générique
specialBirthday :: Int -> String
specialBirthday age = case age of
    1  -> "Joyeux premier anniversaire ! "
    18 -> "Félicitations pour tes 18 ans "
    60 -> "Joyeux anniversaire pour tes 60 ans "
    _  -> "Joyeux anniversaire pour tes " ++ show age ++ " ans ! "

-- Programme principal pour tester
main :: IO ()
main = do
    putStrLn $ specialBirthday 1
    putStrLn $ specialBirthday 18
    putStrLn $ specialBirthday 60
    putStrLn $ specialBirthday 25
    putStrLn $ specialBirthday 100
```

###  Explications

* `case age of` = teste les différents âges spécifiques
* `1`, `18`, `60` = **patterns précis** avec message particulier
* `_` = **tous les autres âges** → message générique
* `show age` = convertit le nombre en **chaîne de caractères** pour l’afficher dans le message
* `++` = concatène les chaînes pour former le message complet


###  Résultats attendus

```
Joyeux premier anniversaire ! 
Félicitations pour tes 18 ans 
Joyeux anniversaire pour tes 60 ans 
Joyeux anniversaire pour tes 25 ans ! 
Joyeux anniversaire pour tes 100 ans ! 
```
