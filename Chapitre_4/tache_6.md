##  HC4T6 – Tâche 6 : Identifier le contenu d’une liste par pattern matching

###  Objectif

Créer une fonction `whatsInsideThisList :: [a] -> String` qui :

1. Prend en entrée une **liste** de n’importe quel type
2. Retourne un message selon le **nombre d’éléments** dans la liste :

   * Liste vide `[]` → `"La liste est vide"`
   * Liste avec **un seul élément** → `"La liste contient un seul élément"`
   * Liste avec **deux éléments** → `"La liste contient exactement deux éléments"`
   * Liste avec **trois éléments ou plus** → `"La liste est longue"`
3. Utilise le **pattern matching** pour identifier les différents cas.


###  Exemple corrigé avec `case` et pattern matching

```haskell
-- Fichier : Main.hs

-- Fonction pour décrire le contenu d'une liste
whatsInsideThisList :: [a] -> String
whatsInsideThisList liste = case liste of
    []      -> "La liste est vide"
    [_]     -> "La liste contient un seul élément"
    [_, _]  -> "La liste contient exactement deux éléments"
    _       -> "La liste est longue"

-- Programme principal pour tester
main :: IO ()
main = do
    putStrLn $ whatsInsideThisList ([] :: [Int])
    putStrLn $ whatsInsideThisList [42]
    putStrLn $ whatsInsideThisList [1,2]
    putStrLn $ whatsInsideThisList [1,2,3,4]
```

###  Explications

* `case liste of` = permet de **tester tous les cas possibles**
* `[]` = correspond à une **liste vide**
* `[_]` = correspond à une **liste avec un seul élément**
* `[_, _]` = correspond à une **liste avec exactement deux éléments**
* `_` = correspond à **toutes les autres listes** (3 éléments ou plus)
* `:: [Int]` = sert à préciser le type pour la liste vide afin d’éviter une erreur de type


###  Résultats attendus

```
La liste est vide
La liste contient un seul élément
La liste contient exactement deux éléments
La liste est longue
```
