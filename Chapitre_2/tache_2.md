# HC2T2 - Tâche 2 : Signatures de fonctions

## Objectif

Écrire les **signatures** et les **implémentations** de trois fonctions simples en Haskell :

1. `add` → somme de deux entiers.
2. `isEven` → vérifie si un entier est pair.
3. `concatStrings` → concatène deux chaînes de caractères.

## Correction complète avec `Main.hs`

```haskell
-- Fichier : Main.hs

-- 1. Addition de deux entiers
add :: Int -> Int -> Int
add x y = x + y

-- 2. Vérifie si un entier est pair
isEven :: Int -> Bool
isEven n = n `mod` 2 == 0

-- 3. Concatène deux chaînes de caractères
concatStrings :: String -> String -> String
concatStrings s1 s2 = s1 ++ s2

-- Fonction principale pour tester
main :: IO ()
main = do
    -- Test add
    print ("add 3 5 = " ++ show (add 3 5))

    -- Test isEven
    print ("isEven 4 = " ++ show (isEven 4))
    print ("isEven 7 = " ++ show (isEven 7))

    -- Test concatStrings
    print ("concatStrings \"Hello\" \" World\" = " ++ concatStrings "Hello" " World")

## Explication ligne par ligne

### `add :: Int -> Int -> Int`

* Signature : prend deux `Int` et retourne un `Int`.
* Définition : `add x y = x + y`.

### `isEven :: Int -> Bool`

* Signature : prend un `Int` et retourne un `Bool`.
* Définition : utilise `mod` pour vérifier si le reste de la division par 2 est nul.

### `concatStrings :: String -> String -> String`

* Signature : prend deux `String` et retourne un `String`.
* Définition : utilise `++` pour concaténer les deux chaînes.

### `main`

* Appelle et affiche les résultats avec `print` et `show`.

## Résultat attendu à l’exécution

"add 3 5 = 8"
"isEven 4 = True"
"isEven 7 = False"
"concatStrings \"Hello\" \" World\" = Hello World"
