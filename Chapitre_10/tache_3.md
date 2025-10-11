### **HC10T3 - Classe de type Comparable**

**Sujet**

* Définir une classe de type `Comparable` avec une fonction :

  ```haskell
  compareWith :: a -> a -> Ordering
  ```
* Implémenter cette classe pour le type `Blockchain`.

---

**Correction complète**

```haskell
-- Fichier : Main.hs

-- Définition d'un type Blockchain simple
data Blockchain = Blockchain
    { chainLength :: Int
    , name        :: String
    } deriving (Show)

-- Définition de la classe Comparable
class Comparable a where
    compareWith :: a -> a -> Ordering

-- Instance Comparable pour Blockchain
instance Comparable Blockchain where
    compareWith b1 b2 = compare (chainLength b1) (chainLength b2)

-- Fonction principale pour tester
main :: IO ()
main = do
    let bc1 = Blockchain 10 "ChainA"
        bc2 = Blockchain 15 "ChainB"
    putStrLn $ "Comparaison de bc1 et bc2 : " ++ show (compareWith bc1 bc2)
```

---

**Explication**

* `data Blockchain = Blockchain { chainLength :: Int, name :: String }` : définit un type Blockchain avec la longueur de la chaîne et un nom.
* `class Comparable a where compareWith :: a -> a -> Ordering` : crée une classe de type pour comparer deux valeurs du même type.
* `instance Comparable Blockchain` : compare deux blockchains en fonction de `chainLength` avec la fonction standard `compare`.
* `main` : crée deux blockchains et affiche le résultat de la comparaison.

---

**Résultat à l’exécution**

```
Comparaison de bc1 et bc2 : LT
```

> Ici, `LT` signifie que `bc1` est plus petit que `bc2` en termes de `chainLength`.

---
