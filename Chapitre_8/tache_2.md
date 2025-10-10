**HC8T2 - Tâche 2 : Types personnalisés et constructeurs de données**

**Sujet**

* Définir un nouveau type `PaymentMethod` avec les constructeurs `Cash`, `Card` et `Cryptocurrency`.
* Créer un type `Person` qui inclut un nom, une adresse (tuple `String` et `Int`), et une méthode de paiement.
* Créer une personne `bob` qui paie en espèces.

---

**Correction complète**

```haskell
-- Main.hs

-- Définition du type PaymentMethod
data PaymentMethod = Cash | Card | Cryptocurrency
    deriving (Show, Eq)

-- Définition du type Person
data Person = Person
    { name :: String
    , address :: (String, Int)  -- (rue, numéro)
    , payment :: PaymentMethod
    } deriving (Show, Eq)

-- Création d'une personne bob qui paie en espèces
bob :: Person
bob = Person
    { name = "Bob"
    , address = ("123 Rue Principale", 10)
    , payment = Cash
    }

-- Fonction principale pour tester
main :: IO ()
main = do
    putStrLn $ "Informations sur Bob : " ++ show bob
```

---

**Explication**

* `data PaymentMethod = Cash | Card | Cryptocurrency` : type énuméré pour les méthodes de paiement.
* `data Person = Person { ... }` : type record avec un nom (`String`), une adresse (tuple `String, Int`), et une méthode de paiement (`PaymentMethod`).
* `bob` : instance de `Person` avec `Cash` comme méthode de paiement.
* `deriving (Show, Eq)` : permet d’afficher les données et de les comparer.

---

**Exemple de résultat à l’exécution**

```
Informations sur Bob : Person {name = "Bob", address = ("123 Rue Principale",10), payment = Cash}
```
