**HC8T8 - Tâche 8 : Synonymes de type et fonction de salutation**

**Sujet**

* Créer des synonymes de type :

  * `Name` pour `String`
  * `Age` pour `Int`
* Définir une fonction `greet :: Name -> Age -> String` qui prend un nom et un âge et retourne un message de salutation.

---

**Correction complète**

```haskell
-- Main.hs

-- Synonymes de type
type Name = String
type Age = Int

-- Fonction de salutation
greet :: Name -> Age -> String
greet name age = "Bonjour " ++ name ++ "! Vous avez " ++ show age ++ " ans."

-- Exemple d'utilisation
main :: IO ()
main = do
    putStrLn $ greet "Alice" 25
    putStrLn $ greet "Bob" 30
```

---

**Explication**

* `type Name = String` et `type Age = Int` définissent des alias pour rendre le code plus lisible.
* `greet name age` utilise `++` pour concaténer des chaînes et `show` pour convertir l’`Int` en `String`.
* `main` montre comment appeler `greet` avec différents noms et âges.

---

**Exemple de résultat à l’exécution**

```
Bonjour Alice! Vous avez 25 ans.
Bonjour Bob! Vous avez 30 ans.
```
