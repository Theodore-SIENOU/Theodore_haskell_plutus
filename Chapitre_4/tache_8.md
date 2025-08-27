##  HC4T8 – Tâche 8 : Extraire des valeurs de tuples

###  Objectif

Créer une fonction `decrireTuple :: (String, Int) -> String` qui :

1. Prend en entrée un **tuple** `(nom, âge)`
2. Retourne une **phrase descriptive** du type `"Alice a 25 ans."`
3. Utilise le **pattern matching** pour extraire directement les valeurs du tuple

###  Exemple corrigé avec `case` et pattern matching

```haskell
-- Fichier : Main.hs

-- Fonction pour décrire un tuple (nom, âge)
decrireTuple :: (String, Int) -> String
decrireTuple tuple = case tuple of
    (nom, age) -> nom ++ " a " ++ show age ++ " ans."

-- Programme principal pour tester
main :: IO ()
main = do
    putStrLn $ decrireTuple ("Alice", 25)
    putStrLn $ decrireTuple ("Bob", 18)
    putStrLn $ decrireTuple ("Charlie", 60)
```

###  Explications

* `case tuple of` = permet de **décomposer le tuple** en ses éléments.
* `(nom, age)` = pattern matching pour accéder directement au **nom** et à l’**âge**.
* `++` = concatène les chaînes.
* `show age` = convertit le nombre `age` en **chaîne de caractères** pour l’afficher.


###  Résultats attendus

```
Alice a 25 ans.
Bob a 18 ans.
Charlie a 60 ans.
```
