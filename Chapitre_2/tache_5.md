HC2T5 - Tâche 5 : et utiliser des fonctions


 **Objectif**

* Définir deux fonctions en Haskell :

  1. `cercleArea` : calcule l’aire d’un cercle à partir de son rayon.
  2. `maxOfThree` : retourne le maximum parmi trois entiers.
* Tester ces fonctions avec plusieurs valeurs.

---

 **Correction complète avec `main`**

```haskell
-- Fichier : Main.hs

-- Calcule l'aire d'un cercle à partir de son rayon
cercleArea :: Float -> Float
cercleArea r = pi * r * r

-- Retourne le maximum de trois entiers
maxOfThree :: Int -> Int -> Int -> Int
maxOfThree x y z = max x (max y z)

-- Fonction principale pour tester
main :: IO ()
main = do
    putStrLn " Test de cercleArea"
    print ("cercleArea 1.0 = " ++ show (cercleArea 1.0))
    print ("cercleArea 3.0 = " ++ show (cercleArea 3.0))
    print ("cercleArea 5.0 = " ++ show (cercleArea 5.0))

    putStrLn "\n Test de maxOfThree"
    print ("maxOfThree 1 2 3 = " ++ show (maxOfThree 1 2 3))
    print ("maxOfThree 10 5 7 = " ++ show (maxOfThree 10 5 7))
    print ("maxOfThree 42 42 21 = " ++ show (maxOfThree 42 42 21))
```

---

 **Explication ligne par ligne**

###  `cercleArea`

```haskell
cercleArea :: Float -> Float
cercleArea r = pi * r * r


* Type `Float -> Float` : prend un rayon (`Float`) et retourne un résultat (`Float`).
* `pi` est une constante prédéfinie en Haskell.
* Formule de l’aire d’un cercle = π × r².

###  `maxOfThree`

```haskell
maxOfThree :: Int -> Int -> Int -> Int
maxOfThree x y z = max x (max y z)


* Type `Int -> Int -> Int -> Int` : prend 3 entiers, retourne 1 entier.
* Utilise la fonction standard `max`.
* Compare d’abord `y` et `z`, puis compare le résultat avec `x`.

###  `main`

* `putStrLn` : affiche du texte.
* `print ("..." ++ show (...))` : affiche à la fois l’expression et le résultat calculé.


 **Résultat attendu à l’exécution**


 Test de cercleArea
"cercleArea 1.0 = 3.1415927"
"cercleArea 3.0 = 28.274334"
"cercleArea 5.0 = 78.53982"

 Test de maxOfThree
"maxOfThree 1 2 3 = 3"
"maxOfThree 10 5 7 = 10"
"maxOfThree 42 42 21 = 42"
