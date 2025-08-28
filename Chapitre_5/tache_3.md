##  HC5T3 – Tâche 3 : Vérifier la présence de majuscules

###  Objectif

Créer une fonction qui :

1. Prend en entrée une **liste de mots** (`[String]`).
2. Vérifie si **au moins un mot commence par une majuscule**.
3. Utilise la fonction d’ordre supérieur **`any`** et une **fonction lambda** ou `isUpper` pour effectuer la vérification.


###  Exemple corrigé avec `any` et lambda

```haskell
-- Fichier : Main.hs
import Data.Char (isUpper)

-- Fonction pour vérifier la présence d'un mot commençant par une majuscule
hasCapitalWord :: [String] -> Bool
hasCapitalWord = any (\word -> not (null word) && isUpper (head word))

-- Programme principal pour tester
main :: IO ()
main = do
    print $ hasCapitalWord ["bonjour", "monde"]       -- False
    print $ hasCapitalWord ["hello", "World"]        -- True
    print $ hasCapitalWord ["Haskell", "est", "fun"] -- True
    print $ hasCapitalWord ["", "empty"]             -- False
```


###  Explications

* `any` = retourne `True` si **au moins un élément** de la liste satisfait la condition.
* `\word -> ...` = **fonction lambda** qui teste chaque mot.
* `not (null word)` = vérifie que le mot n’est pas vide.
* `isUpper (head word)` = vérifie que **la première lettre** est une majuscule.
* La fonction peut traiter des listes de mots vides sans provoquer d’erreur.


###  Résultats attendus

```
False
True
True
False
```
