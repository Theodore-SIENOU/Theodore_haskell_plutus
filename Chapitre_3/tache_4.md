**HC3T4 – Tâche 4 : Aire d’un triangle avec la formule de Héron**

---

###  Objectif

* Définir une fonction `triangleArea` qui :

  * prend trois côtés `a`, `b`, `c` (type `Float`)
  * utilise **let** pour calculer le demi-périmètre `s`
  * applique la **formule de Héron** :

    $$
    \text{aire} = \sqrt{s \cdot (s-a) \cdot (s-b) \cdot (s-c)}
    $$
* Tester avec :

  * `triangleArea 3 4 5`
  * `triangleArea 7 8 9`

---

###  Correction complète avec `main`

```haskell
-- Fichier : Main.hs

-- Calcule l'aire d'un triangle à partir de ses côtés
triangleArea :: Float -> Float -> Float -> Float
triangleArea a b c =
    let s = (a + b + c) / 2
    in sqrt (s * (s - a) * (s - b) * (s - c))

-- Fonction principale pour tester
main :: IO ()
main = do
    putStrLn $ "triangleArea 3 4 5 = " ++ show (triangleArea 3 4 5)
    putStrLn $ "triangleArea 7 8 9 = " ++ show (triangleArea 7 8 9)
```

---

###  Explication ligne par ligne

```haskell
triangleArea :: Float -> Float -> Float -> Float
```

* La fonction prend trois **Floats** et retourne un **Float** (l’aire).

```haskell
let s = (a + b + c) / 2
```

* Calcul du **demi-périmètre** `s`.

```haskell
sqrt (s * (s - a) * (s - b) * (s - c))
```

* Formule de Héron pour calculer l’aire.
* `sqrt` calcule la racine carrée.

---

###  Résultat attendu à l’exécution

```
triangleArea 3 4 5 = 6.0
triangleArea 7 8 9 = 26.832815
```
