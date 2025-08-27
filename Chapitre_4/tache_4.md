##  HC4T4 – Tâche 4 : `specialBirthday` avec pattern matching

###  Objectif

Créer une fonction `specialBirthday :: Int -> String` qui :

1. Prend en entrée un **âge**
2. Retourne un **message spécial** pour certains âges précis :

   * `1` → `"Joyeux premier anniversaire !"`
   * `18` → `"Félicitations pour ta majorité !"`
   * `60` → `"Joyeux anniversaire pour tes 60 ans !"`
3. Pour tous les autres âges, retourne un message **générique** `"Joyeux anniversaire !"`
4. Utilise le **pattern matching** au lieu des `if-else`.

---

###  Exemple corrigé avec `case` et pattern matching

```haskell
-- Fichier : Main.hs

-- Fonction anniversaire spéciale
specialBirthday :: Int -> String
specialBirthday age = case age of
    1  -> "Joyeux premier anniversaire ! 🎂"
    18 -> "Félicitations pour tes 18 ans 🎉"
    60 -> "Joyeux anniversaire pour tes 60 ans 🎊"
    _  -> "Joyeux anniversaire ! 🎁"

-- Programme principal pour tester
main :: IO ()
main = do
    putStrLn $ specialBirthday 1
    putStrLn $ specialBirthday 18
    putStrLn $ specialBirthday 60
    putStrLn $ specialBirthday 25
```


###  Explications

* `case age of` = permet de **tester plusieurs valeurs d’âge**
* Chaque nombre spécifique est un **pattern** qui retourne un message précis
* `_` = correspond à **tous les autres âges non définis**
* `🎂🎉🎊🎁` = emoji pour rendre le message plus visuel (facultatif)


###  Résultats attendus

```
Joyeux premier anniversaire ! 🎂
Félicitations pour tes 18 ans 🎉
Joyeux anniversaire pour tes 60 ans 🎊
Joyeux anniversaire ! 🎁
```
