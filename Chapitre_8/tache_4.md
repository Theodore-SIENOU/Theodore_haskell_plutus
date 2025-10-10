**HC8T4 - Tâche 4 : Syntaxe d’enregistrement pour Employee**

**Sujet**

* Définir un nouveau type `Employee` en syntaxe d’enregistrement, avec les champs `name :: String` et `experienceInYears :: Float`.
* Créer un employé `richard` avec 7,5 ans d’expérience.

---

**Correction complète**

```haskell
-- Main.hs

-- Définition du type Employee avec syntaxe d'enregistrement
data Employee = Employee
    { name :: String
    , experienceInYears :: Float
    } deriving (Show, Eq)

-- Création d'un employé
richard :: Employee
richard = Employee { name = "Richard", experienceInYears = 7.5 }

-- Fonction principale pour tester
main :: IO ()
main = do
    putStrLn $ "Employé : " ++ name richard
    putStrLn $ "Années d'expérience : " ++ show (experienceInYears richard)
```

---

**Explication**

* `data Employee = Employee { name :: String, experienceInYears :: Float }` : définit un type avec des champs nommés (record syntax).
* `richard = Employee { name = "Richard", experienceInYears = 7.5 }` : crée un employé en initialisant ses champs.
* `main` : affiche les informations de l’employé avec `putStrLn` et `show` pour convertir le Float en chaîne.

---

**Exemple de résultat à l’exécution**

```
Employé : Richard
Années d'expérience : 7.5
```
