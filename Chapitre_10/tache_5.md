### HC10T5 - Classe de type ShowDetailed

**Sujet**

Définir une classe de type `ShowDetailed` avec une fonction `showDetailed :: a -> String`.
Créer un type `User` avec des champs `name :: String` et `age :: Int` et implémenter `ShowDetailed` pour ce type.

---

**Correction complète**

```haskell
-- Fichier : Main.hs

-- Définition de la classe ShowDetailed
class ShowDetailed a where
    showDetailed :: a -> String

-- Définition du type User
data User = User { name :: String, age :: Int } deriving (Show)

-- Implémentation de ShowDetailed pour User
instance ShowDetailed User where
    showDetailed (User n a) = "User name: " ++ n ++ ", age: " ++ show a

-- Fonction principale pour tester
main :: IO ()
main = do
    let user1 = User "Alice" 30
        user2 = User "Bob" 25
    putStrLn $ showDetailed user1
    putStrLn $ showDetailed user2
```

---

**Explication**

* `class ShowDetailed a where showDetailed :: a -> String` : définit une classe de type pour afficher des informations détaillées.
* `data User = User { name :: String, age :: Int }` : type avec syntaxe d’enregistrement.
* `instance ShowDetailed User` : implémente la fonction `showDetailed` pour `User`.
* `showDetailed (User n a)` : construit une chaîne contenant le nom et l’âge de l’utilisateur.
* `putStrLn $ showDetailed user1` : affiche le détail de l’utilisateur dans la console.

---

**Résultat à l’exécution**

```
User name: Alice, age: 30
User name: Bob, age: 25
```

---
