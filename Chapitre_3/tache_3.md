 **HC3T3 – Tâche 3 : Convertir une couleur RGB en chaîne hexadécimale avec let**


###  Objectif

* Définir une fonction `rgbToHex` qui :

  * prend un **triplet `(Int, Int, Int)`** représentant les valeurs R, G, B (0–255)
  * utilise des **let** pour convertir chaque composant en **chaîne hexadécimale** à deux caractères
  * concatène les trois valeurs pour obtenir une seule chaîne hexadécimale
* Tester avec :

  * `rgbToHex (255, 0, 127)`
  * `rgbToHex (0, 255, 64)`

---

### 🔹 Correction complète avec `main`

```haskell
-- Fichier : Main.hs

import Text.Printf (printf)

-- Convertit un triplet RGB en chaîne hexadécimale
rgbToHex :: (Int, Int, Int) -> String
rgbToHex (r, g, b) =
    let hexR = printf "%02X" r
        hexG = printf "%02X" g
        hexB = printf "%02X" b
    in "#" ++ hexR ++ hexG ++ hexB

-- Fonction principale pour tester
main :: IO ()
main = do
    putStrLn $ "rgbToHex (255,0,127) = " ++ rgbToHex (255,0,127)
    putStrLn $ "rgbToHex (0,255,64) = " ++ rgbToHex (0,255,64)
```

---

### 🔹 Explication ligne par ligne

```haskell
rgbToHex :: (Int, Int, Int) -> String
```

* La fonction prend un **triplet d’entiers** et retourne une **chaîne**.

```haskell
let hexR = printf "%02X" r
    hexG = printf "%02X" g
    hexB = printf "%02X" b
```

* `printf "%02X"` convertit un entier en **hexadécimal sur 2 chiffres**, avec `0` si nécessaire.
* `hexR`, `hexG`, `hexB` sont les valeurs intermédiaires pour R, G, B.

```haskell
in "#" ++ hexR ++ hexG ++ hexB
```

* Concatène les trois valeurs hexadécimales avec un `#` au début.

---

### 🔹 Résultat attendu à l’exécution

```
rgbToHex (255,0,127) = #FF007F
rgbToHex (0,255,64) = #00FF40
```
