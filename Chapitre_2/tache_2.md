##  HC2T2 – Tâche 2 : Signatures de fonctions

###  Objectif

1. Définir les **signatures de fonctions** en Haskell.
2. Implémenter les fonctions suivantes :

   * `add` : prend deux `Int` et retourne leur somme.
   * `isEven` : prend un `Int` et retourne un `Bool` indiquant si le nombre est pair.
   * `concatStrings` : prend deux `String` et retourne leur concaténation.


###  Code avec signatures et implémentations

```haskell
-- Fichier : Main.hs

-- Fonction qui additionne deux entiers
add :: Int -> Int -> Int
add x y = x + y

-- Fonction qui vérifie si un entier est pair
isEven :: Int -> Bool
isEven n = n `mod` 2 == 0

-- Fonction qui concatène deux chaînes de caractères
concatStrings :: String -> String -> String
concatStrings s1 s2 = s1 ++ s2

-- Programme principal pour tester
main :: IO ()
main = do
    print $ add 5 7                    -- 12
    print $ isEven 10                  -- True
    print $ isEven 7                   -- False
    print $ concatStrings "Hello, " "World!"  -- "Hello, World!"
```


###  Explications

1. **Signature `add :: Int -> Int -> Int`**

   * La fonction prend deux entiers (`Int`, `Int`) et retourne un entier (`Int`).
   * Exemple : `add 5 7 = 12`.

2. **Signature `isEven :: Int -> Bool`**

   * La fonction prend un entier et retourne un booléen.
   * `n \`mod\` 2 == 0`vérifie si`n\` est divisible par 2.

3. **Signature `concatStrings :: String -> String -> String`**

   * La fonction prend deux chaînes et retourne leur concaténation.
   * L’opérateur `++` est utilisé pour coller deux chaînes.


###  Résultats attendus

```
12
True
False
"Hello, World!"
```
