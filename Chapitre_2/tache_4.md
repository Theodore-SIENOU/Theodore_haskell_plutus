HC2T4 - Tâche 4 : Notation préfixe et infixe



 **Objectif**

* Réécrire des opérations en **notation préfixe** et en **notation infixe**.
* En Haskell :

  * **infixe** = on écrit l’opérateur entre ses arguments (ex. `5 + 3`).
  * **préfixe** = on écrit l’opérateur ou la fonction avant les arguments (ex. `(+) 5 3`).
  * Pour une fonction à deux arguments, on peut la mettre **entre backticks \`f\`** pour l’utiliser en infixe.

---

 **Correction complète avec `main`**

```haskell
-- Fichier : Main.hs

-- Fonction d'exemple (pour la notation infixe)
myMin :: Int -> Int -> Int
myMin x y = if x < y then x else y

myAnd :: Bool -> Bool -> Bool
myAnd x y = if x then y else False

-- Fonction principale pour tester
main :: IO ()
main = do
    putStrLn " Notation préfixe :"
    print ((&&) True False)  -- équivalent à True && False
    print ((&&) True True)   -- équivalent à True && True
    print ((+) 5 3)          -- équivalent à 5 + 3
    print ((-) 10 4)         -- équivalent à 10 - 4

    putStrLn "\n Notation infixe :"
    print (7 `myMin` 2)      -- équivalent à myMin 7 2
    print (6 `myMin` 5)      -- équivalent à myMin 6 5
    print (True `myAnd` False) -- équivalent à myAnd True False
```

---

 **Explication ligne par ligne**

###  Notation préfixe

* `(+) 5 3` → applique `+` en mode préfixe.
* `(-) 10 4` → applique `-` en mode préfixe.
* `(&&) True False` → applique `&&` en mode préfixe.

###  Notation infixe

* ``7 `myMin` 2`` → applique `myMin` en mode infixe.
* ``True `myAnd` False`` → applique `myAnd` en mode infixe.

---

 **Résultat attendu à l’exécution**

```
 Notation préfixe :
False
True
8
6

 Notation infixe :
2
5
False
