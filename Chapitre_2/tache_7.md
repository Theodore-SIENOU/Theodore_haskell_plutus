HC2T7 - Tâche 7 : Expressions booléennes

###  Objectif

* Écrire et tester des expressions booléennes simples en Haskell :

  1. `True && True`
  2. `False || True`
  3. `not True`
  4. Une comparaison qui retourne `False` (ex. `5 > 10`).

---

###  Correction complète avec `main`

```haskell
-- Fichier : Main.hs

main :: IO ()
main = do
    putStrLn " Expressions booléennes en Haskell"

    -- True && True
    print ("True && True = " ++ show (True && True))

    -- False || True
    print ("False || True = " ++ show (False || True))

    -- not True
    print ("not True = " ++ show (not True))

    -- Comparaison qui retourne False
    print ("5 > 10 = " ++ show (5 > 10))
```

---

###  Explications

1. `True && True`

   * L’opérateur logique **ET** (`&&`).
   * Seulement vrai si les deux sont vrais → résultat = `True`.

2. `False || True`

   * L’opérateur logique **OU** (`||`).
   * Résultat = `True` (car au moins une valeur est vraie).

3. `not True`

   * L’opérateur de **négation** logique.
   * Inverse la valeur → résultat = `False`.

4. `5 > 10`

   * Comparaison numérique.
   * Comme `5` n’est pas supérieur à `10`, résultat = `False`.

---

###  Exemple de sortie attendue

```
 Expressions booléennes en Haskell
"True && True = True"
"False || True = True"
"not True = False"
"5 > 10 = False"
