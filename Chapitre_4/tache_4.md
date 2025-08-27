**HC4T4 – Tâche 4 :  Réspécifiti spécialBirthday avec le pattern matching**

 Objectif
Réécrire une fonction `specialBirthday :: Int -> String` qui prend un âge en entrée et retourne un message spécial avec **pattern matching** (au lieu de `if-else`).

* `1` → `"Joyeux premier anniversaire !"`
* `18` → `"Félicitations pour ta majorité !" `
* `60` → `"Joyeux anniversaire pour tes 60 ans !" `
* Sinon → `"Joyeux anniversaire !" `

 Correction complète avec `main`

```haskell
-- Définition de la fonction
specialBirthday :: Int -> String
specialBirthday age =
  case age of
    1  -> "Joyeux premier anniversaire !"
    18 -> "Félicitations pour ta majorité !"
    60 -> "Joyeux anniversaire pour tes 60 ans !"
    _  -> "Joyeux anniversaire !"

-- Programme principal pour tester
main :: IO ()
main = do
  putStrLn (specialBirthday 1)
  putStrLn (specialBirthday 18)
  putStrLn (specialBirthday 60)
  putStrLn (specialBirthday 25)
```
