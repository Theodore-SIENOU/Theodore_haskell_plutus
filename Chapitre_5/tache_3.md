**HC5T3 – Vérifier la présence de majuscules**.

On doit écrire une fonction qui utilise **`any`** pour vérifier si une **liste de mots**
contient **au moins un mot commençant par une majuscule**.


###  Solution en Haskell

```haskell
import Data.Char (isUpper)

hasCapitalizedWord :: [String] -> Bool
hasCapitalizedWord words = any startsWithUpper words
  where
    startsWithUpper []     = False         -- mot vide → pas de majuscule
    startsWithUpper (c:_)  = isUpper c     -- vérifie si le 1er caractère est une majuscule
```

###  Explication

* `any f liste` retourne `True` si **au moins un élément** de la liste satisfait le prédicat `f`.
* Ici, le prédicat `startsWithUpper` teste si le premier caractère est une majuscule (`isUpper`).
* Les mots vides (`""`) sont ignorés (retournent `False`).


###  Exemple de test

```haskell
main :: IO ()
main = do
    print (hasCapitalizedWord ["hello", "world"])        -- False
    print (hasCapitalizedWord ["bonjour", "Paris"])      -- True
    print (hasCapitalizedWord ["java", "haskell", "C"])  -- True
    print (hasCapitalizedWord ["", "python"])            -- False
```

###  Résultats attendus

```
False
True
True
False
```
