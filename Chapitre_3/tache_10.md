**HC3T10 – Tâche avancée 10 :  Vérifier si une chaîne est un palindrome (récursion, gardes)**

###  Objectif

* Définir une fonction `isPalindrome` qui :

  * prend une chaîne (`String`)
  * retourne `True` si la chaîne est un palindrome, `False` sinon
  * utilise **récursion** et **gardes (`|`)** :

    1. Chaîne vide ou un caractère → `True`
    2. Premier et dernier caractère égaux → vérifier la sous-chaîne centrale
    3. Sinon → `False`

* Tester avec :

  * `isPalindrome "racecar"`
  * `isPalindrome "haskell"`
  * `isPalindrome "madam"`

---

###  Correction complète avec `main`

```haskell
-- Fichier : Main.hs

-- Vérifie si une chaîne est un palindrome
isPalindrome :: String -> Bool
isPalindrome str
    | length str <= 1 = True
    | head str == last str = isPalindrome (init (tail str))
    | otherwise = False

-- Fonction principale pour tester
main :: IO ()
main = do
    putStrLn $ "isPalindrome \"racecar\" = " ++ show (isPalindrome "racecar")
    putStrLn $ "isPalindrome \"haskell\" = " ++ show (isPalindrome "haskell")
    putStrLn $ "isPalindrome \"madam\" = " ++ show (isPalindrome "madam")
```

---

###  Explication ligne par ligne

```haskell
isPalindrome :: String -> Bool
```

* La fonction prend une **chaîne** et retourne un **Bool**.

```haskell
| length str <= 1 = True
```

* Une chaîne vide ou d’un caractère est toujours un palindrome.

```haskell
| head str == last str = isPalindrome (init (tail str))
```

* Compare le **premier et dernier caractère**.
* Si égaux, vérifie **récursivement** la sous-chaîne centrale.

```haskell
| otherwise = False
```

* Sinon, ce n’est pas un palindrome.

---

###  Résultat attendu à l’exécution

```
isPalindrome "racecar" = True
isPalindrome "haskell" = False
isPalindrome "madam" = True
