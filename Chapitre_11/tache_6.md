**HC11T6 - Tâche 6 : Classe `AdvancedEq` pour `Blockchain`**

**Sujet**

Définir une classe de type `AdvancedEq` qui étend `Eq` et ajoute une méthode `compareEquality`. Implémenter cette classe pour le type `Blockchain` afin de comparer deux chaînes de blocs et retourner un message décrivant si elles sont identiques ou non.

---

**Correction complète**

```haskell
-- Main.hs

-- Définition de la classe AdvancedEq
class Eq a => AdvancedEq a where
    compareEquality :: a -> a -> String

-- Exemple de type Blockchain
data Blockchain = Blockchain [String] deriving (Show, Eq)

-- Implémentation de AdvancedEq pour Blockchain
instance AdvancedEq Blockchain where
    compareEquality bc1 bc2 =
        if bc1 == bc2
            then "Blockchains are identical!"
            else "Blockchains differ!"

-- Fonction main pour tester
main :: IO ()
main = do
    let chain1 = Blockchain ["Block1", "Block2", "Block3"]
        chain2 = Blockchain ["Block1", "Block2", "Block3"]
        chain3 = Blockchain ["Block1", "BlockX", "Block3"]

    putStrLn $ compareEquality chain1 chain2
    putStrLn $ compareEquality chain1 chain3
```

---

**Explication**

* `class Eq a => AdvancedEq a` :

  * Déclare une nouvelle classe `AdvancedEq` qui hérite de `Eq`, donc tous les types qui l’implémentent doivent déjà être comparables avec `(==)` et `(/=)`.
* `compareEquality :: a -> a -> String` :

  * Méthode qui compare deux valeurs du même type et retourne un message `String`.
* `data Blockchain = Blockchain [String]` :

  * Type simple représentant une blockchain comme une liste de blocs (ici des `String`).
* `instance AdvancedEq Blockchain` :

  * Compare deux blockchains avec `(==)` et retourne un message adapté.
* `main` :

  * Teste `compareEquality` avec deux blockchains identiques et deux différentes.

---

**Exemple de résultat à l’exécution**

```
Blockchains are identical!
Blockchains differ!
```

---
