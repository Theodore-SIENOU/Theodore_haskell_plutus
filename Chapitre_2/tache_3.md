HC2T3 - Tâche 3 : Variables d'économie



 **Objectif**

* Définir des **variables immuables** en Haskell :

  * `myAge` comme un `Int`
  * `piValue` comme un `Double`
  * `salutation` comme un `String`
  * `isHaskellFun` comme un `Bool`
* Tester ce qui se passe si on essaie de les **modifier** (spoiler : impossible, car Haskell a des variables **immutables**).


 **Correction complète avec `main`**

```haskell
-- Fichier : Main.hs

-- Variables immuables
myAge :: Int
myAge = 25

piValue :: Double
piValue = 3.14159

salutation :: String
salutation = "Bonjour, Haskell!"

isHaskellFun :: Bool
isHaskellFun = True

-- Fonction principale pour tester
main :: IO ()
main = do
    putStrLn $ "Mon âge est : " ++ show myAge
    putStrLn $ "La valeur de pi est : " ++ show piValue
    putStrLn $ "Salutation : " ++ salutation
    putStrLn $ "Est-ce que Haskell est fun ? " ++ show isHaskellFun

    -- Essayons de modifier myAge (décommente pour tester)
    -- myAge = 30   -- ❌ Erreur : les variables sont immuables


 **Explication ligne par ligne**

```haskell
myAge :: Int
myAge = 25
```

* Déclare `myAge` comme un entier (`Int`), fixé à 25.

```haskell
piValue :: Double
piValue = 3.14159
```

* Une valeur flottante (plus précise que `Float`).

```haskell
salutation :: String
salutation = "Bonjour, Haskell!"
```

* Une chaîne de caractères.

```haskell
isHaskellFun :: Bool
isHaskellFun = True
```

* Un booléen.

```haskell
myAge = 30


* ❌ Si tu décommente cette ligne, le compilateur renverra une **erreur** :
  *“Multiple declarations of `myAge`”*.
* Car en Haskell, les **variables sont immuables** (on ne peut pas les réassigner).



✅ **Résultat attendu à l’exécution**


Mon âge est : 25
La valeur de pi est : 3.14159
Salutation : Bonjour, Haskell!
Est-ce que Haskell est fun ? True
