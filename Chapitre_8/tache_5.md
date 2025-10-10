**HC8T5 - Tâche 5 : Syntaxe d’enregistrement pour Person**

**Sujet**

* Définir un type `Person` en syntaxe d’enregistrement incluant `name :: String`, `age :: Int` et `isEmployed :: Bool`.
* Créer un `person1` qui est employé, et un `person2` qui est sans emploi.

---

**Correction complète**

```haskell
-- Main.hs

-- Définition du type Person avec syntaxe d'enregistrement
data Person = Person
    { name :: String
    , age :: Int
    , isEmployed :: Bool
    } deriving (Show, Eq)

-- Création de deux personnes
person1 :: Person
person1 = Person { name = "Alice", age = 30, isEmployed = True }

person2 :: Person
person2 = Person { name = "Bob", age = 25, isEmployed = False }

-- Fonction principale pour tester
main :: IO ()
main = do
    putStrLn $ "Personne 1 : " ++ name person1 ++ ", Âge : " ++ show (age person1) ++ ", Employé ? " ++ show (isEmployed person1)
    putStrLn $ "Personne 2 : " ++ name person2 ++ ", Âge : " ++ show (age person2) ++ ", Employé ? " ++ show (isEmployed person2)
```

---

**Explication**

* `data Person = Person { ... }` : crée un type avec des champs nommés pour un accès facile.
* `person1` et `person2` : initialisation des champs avec des valeurs différentes pour l’emploi.
* `main` : utilise `putStrLn` et `show` pour afficher les informations de chaque personne.

---

**Exemple de résultat à l’exécution**

```
Personne 1 : Alice, Âge : 30, Employé ? True
Personne 2 : Bob, Âge : 25, Employé ? False
```
