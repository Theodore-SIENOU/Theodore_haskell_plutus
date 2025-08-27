HC3T1 – Tâche 1 : Vérification d’un nombre**

###  Objectif

* Définir une fonction `checkNumber` qui :

  * prend un `Int` en entrée
  * retourne `"Positif"`, `"Négatif"` ou `"Zéro"` selon le signe du nombre
  * utilise un **if-then-else**

* Tester avec :

  * `checkNumber 5`
  * `checkNumber (-3)`
  * `checkNumber 0`

---

###  Correction complète avec `main`

```haskell
-- Fichier : Main.hs

-- Vérifie si un nombre est positif, négatif ou nul
checkNumber :: Int -> String
checkNumber n = 
    if n > 0 then "Positif"
    else if n < 0 then "Négatif"
    else "Zéro"

-- Fonction principale pour tester
main :: IO ()
main = do
    putStrLn $ "checkNumber 5 = " ++ checkNumber 5
    putStrLn $ "checkNumber (-3) = " ++ checkNumber (-3)
    putStrLn $ "checkNumber 0 = " ++ checkNumber 0
```

---

###  Explication ligne par ligne

```haskell
checkNumber :: Int -> String
```

* La fonction prend un entier (`Int`) et retourne une chaîne (`String`).

```haskell
if n > 0 then "Positif"
else if n < 0 then "Négatif"
else "Zéro"
```

* Condition en **chaînage** :

  1. Si `n > 0` → `"Positif"`
  2. Sinon si `n < 0` → `"Négatif"`
  3. Sinon → `"Zéro"`

```haskell
main = do ...
```

* Affiche le résultat de la fonction avec différentes valeurs de test.

---

###  Résultat attendu à l’exécution

```
checkNumber 5 = Positif
checkNumber (-3) = Négatif
checkNumber 0 = Zéro
