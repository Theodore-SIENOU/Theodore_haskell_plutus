**HC4T5 – Tâche 5 : Ajouter un cas générique avec un message personnalisé**.

##  Exemple corrigé avec `case` et un cas générique

```haskell
-- Fichier : Main.hs

-- Fonction anniversaire spéciale
specialBirthday :: Int -> String
specialBirthday age = case age of
    1  -> "Joyeux premier anniversaire ! 🎂"
    18 -> "Félicitations pour tes 18 ans 🎉"
    60 -> "Joyeux 60ème anniversaire 🎊"
    _  -> "Joyeux anniversaire pour tes " ++ show age ++ " ans ! 🎁"

-- Programme principal pour tester
main :: IO ()
main = do
    putStrLn $ specialBirthday 1
    putStrLn $ specialBirthday 18
    putStrLn $ specialBirthday 60
    putStrLn $ specialBirthday 25
    putStrLn $ specialBirthday 100
```

---

##  Explications

* `case ... of` = permet de tester plusieurs cas.
* `_` = correspond à **tous les autres cas** non définis avant.
* `show age` = convertit un nombre en **chaîne de caractères** pour pouvoir l’afficher dans le message.

---

##  Résultats attendus

```
Joyeux premier anniversaire ! 🎂
Félicitations pour tes 18 ans 🎉
Joyeux 60ème anniversaire 🎊
Joyeux anniversaire pour tes 25 ans ! 🎁
Joyeux anniversaire pour tes 100 ans ! 🎁
```
