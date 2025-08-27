**HC3T8 – Tâche avancée 8 : Calcul de l’IMC**

###  Objectif

* Définir une fonction `bmiCategory` qui :

  * prend le **poids** (`Float`) et la **taille** (`Float`)
  * calcule l’IMC :

    $$
    \text{bmi} = \frac{\text{poids}}{\text{taille}^2}
    $$
  * utilise **`where`** pour stocker la valeur de `bmi`
  * classe l’IMC avec des **gardes (`|`)** :

    * `< 18.5` → `"Maigre"`
    * `18.5–24.9` → `"Normal"`
    * `25–29.9` → `"Surpoids"`
    * `>= 30` → `"Obésité"`

* Tester avec :

  * `bmiCategory 70 1.75`
  * `bmiCategory 90 1.8`

---

###  Correction complète avec `main`

```haskell
-- Fichier : Main.hs

-- Calcule l'IMC et retourne la catégorie
bmiCategory :: Float -> Float -> String
bmiCategory poids taille
    | bmi < 18.5 = "Maigre"
    | bmi <= 24.9 = "Normal"
    | bmi <= 29.9 = "Surpoids"
    | otherwise = "Obésité"
    where bmi = poids / (taille ^ 2)

-- Fonction principale pour tester
main :: IO ()
main = do
    putStrLn $ "bmiCategory 70 1.75 = " ++ bmiCategory 70 1.75
    putStrLn $ "bmiCategory 90 1.8 = " ++ bmiCategory 90 1.8
```

---

###  Explication ligne par ligne

```haskell
bmiCategory :: Float -> Float -> String
```

* La fonction prend **poids** et **taille** (Float) et retourne une **chaîne**.

```haskell
where bmi = poids / (taille ^ 2)
```

* `bmi` est calculé avec la formule standard.
* `^` élève au carré.

```haskell
| bmi < 18.5 = "Maigre"
| bmi <= 24.9 = "Normal"
| bmi <= 29.9 = "Surpoids"
| otherwise = "Obésité"
```

* Les **gardes** classent l’IMC en quatre catégories.

---

###  Résultat attendu à l’exécution

```
bmiCategory 70 1.75 = Normal
bmiCategory 90 1.8 = Surpoids
