##  HC2T3 – Tâche 3 : Variables immuables

###  Objectif

1. Définir des **variables immuables** en Haskell.
2. Comprendre que dans Haskell, une fois une variable définie, **elle ne peut pas être modifiée** (immutabilité).
3. Tester la tentative de modification d’une variable pour observer l’erreur générée.


###  Code Haskell

```haskell
-- Fichier : Main.hs

-- Définition de variables immuables
myAge :: Int
myAge = 20

piValue :: Double
piValue = 3.14159

greeting :: String
greeting = "Hello, Haskell!"

isHaskellFun :: Bool
isHaskellFun = True

-- Programme principal pour afficher les valeurs
main :: IO ()
main = do
    print myAge
    print piValue
    print greeting
    print isHaskellFun

    -- Tentative de "modifier" une variable
    -- Décommentez la ligne suivante pour tester :
    -- myAge = 25
```


###  Explications

1. **Déclaration des variables**

   * `myAge :: Int` → variable entière (20).
   * `piValue :: Double` → valeur flottante avec décimales.
   * `greeting :: String` → une chaîne de caractères.
   * `isHaskellFun :: Bool` → un booléen (`True` ou `False`).

2. **Immutabilité**

   * En Haskell, une variable est une **constante**.
   * Par exemple, `myAge` vaut toujours 20.
   * Si on essaie de réassigner `myAge = 25`, GHCi retournera une **erreur de compilation**.


###  Résultats attendus

En exécutant `main` :

```
20
3.14159
"Hello, Haskell!"
True
```
