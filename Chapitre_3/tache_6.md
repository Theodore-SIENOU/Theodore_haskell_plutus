**HC3T6 – Tâche avancée 6 : Vérification d’une année bissextile**

###  Objectif

* Définir une fonction `isLeapYear` qui :

  * prend une année (`Int`)
  * retourne `True` si c’est une année bissextile, `False` sinon
  * règles :

    1. Divisible par 400 → bissextile
    2. Divisible par 100 mais pas par 400 → non bissextile
    3. Divisible par 4 → bissextile
    4. Sinon → non bissextile
* Tester avec :

  * `isLeapYear 2000`
  * `isLeapYear 1900`
  * `isLeapYear 2024`

---

###  Correction complète avec `main`

```haskell
-- Fichier : Main.hs

-- Vérifie si une année est bissextile
isLeapYear :: Int -> Bool
isLeapYear year =
    if year `mod` 400 == 0 then True
    else if year `mod` 100 == 0 then False
    else if year `mod` 4 == 0 then True
    else False

-- Fonction principale pour tester
main :: IO ()
main = do
    putStrLn $ "isLeapYear 2000 = " ++ show (isLeapYear 2000)
    putStrLn $ "isLeapYear 1900 = " ++ show (isLeapYear 1900)
    putStrLn $ "isLeapYear 2024 = " ++ show (isLeapYear 2024)
```

---

###  Explication ligne par ligne

```haskell
year `mod` 400 == 0
```

* Vérifie si `year` est divisible par 400.

```haskell
else if year `mod` 100 == 0
```

* Vérifie si divisible par 100 mais pas par 400.

```haskell
else if year `mod` 4 == 0
```

* Vérifie si divisible par 4.

```haskell
else False
```

* Sinon → pas bissextile.

---

###  Résultat attendu à l’exécution

```
isLeapYear 2000 = True
isLeapYear 1900 = False
isLeapYear 2024 = True
