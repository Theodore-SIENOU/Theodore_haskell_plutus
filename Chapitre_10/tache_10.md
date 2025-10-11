### **HC10T10 – Classe Concatenatable**

**Sujet :**
Créer une classe de type `Concatenatable` avec une fonction :
`concatWith :: a -> a -> a`
et l’implémenter pour le type `[Char]` (`String`).

---

###  **Correction complète**

```haskell
-- Définition de la classe Concatenatable
class Concatenatable a where
    concatWith :: a -> a -> a

-- Instance pour le type String ([Char])
instance Concatenatable String where
    concatWith s1 s2 = s1 ++ s2

-- Fonction principale pour tester
main :: IO ()
main = do
    let str1 = "Hello, "
    let str2 = "World!"
    putStrLn $ "Résultat de concatWith : " ++ concatWith str1 str2
```

---

###  **Explication**

* `Concatenatable` est une **classe générique** pour tout type qui peut être concaténé.
* L’instance pour `String` utilise simplement l’opérateur `(++)` natif de Haskell.
* Dans `main`, on teste la concaténation de deux chaînes.

---

###  **Résultat attendu**

```
Résultat de concatWith : Hello, World!
```

---
