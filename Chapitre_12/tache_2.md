### **HC12T2 – Additionner deux nombres**

**Sujet :**
Écrire une fonction `addTwoNumbers` qui prend deux entiers en entrée et retourne leur somme.
Le résultat doit être affiché via la fonction `main`.

---

###  **Correction complète**

```haskell
-- Définition de la fonction addTwoNumbers
addTwoNumbers :: Int -> Int -> Int
addTwoNumbers x y = x + y

-- Fonction principale
main :: IO ()
main = do
    let a = 10
    let b = 25
    let result = addTwoNumbers a b
    putStrLn ("La somme de " ++ show a ++ " et " ++ show b ++ " est : " ++ show result)
```

---

###  **Explication**

* `addTwoNumbers` prend deux entiers (`Int`) et retourne leur somme avec l’opérateur `+`.
* `show` convertit les valeurs numériques en chaînes de caractères pour pouvoir les afficher avec `putStrLn`.
* `let` permet de définir des variables locales à l’intérieur d’un bloc `do`.

---

###  **Résultat attendu à l’exécution**

```
La somme de 10 et 25 est : 35
```

---
