**HC8T3 - Tâche 3 : Types algébriques et fonctions**

**Sujet**

* Définir un type `Shape` avec les constructeurs `Circle Float` et `Rectangle Float Float`.
* Créer une fonction `area :: Shape -> Float` qui calcule l’aire de la forme.
* Calculer l’aire d’un cercle de rayon 5 et d’un rectangle de côtés 10 et 5.

---

**Correction complète**

```haskell
-- Main.hs

-- Définition du type Shape
data Shape = Circle Float | Rectangle Float Float
    deriving (Show, Eq)

-- Fonction qui calcule l'aire d'une forme
area :: Shape -> Float
area (Circle r) = pi * r * r
area (Rectangle l w) = l * w

-- Exemples de formes
circleExample :: Shape
circleExample = Circle 5

rectangleExample :: Shape
rectangleExample = Rectangle 10 5

-- Fonction principale pour tester
main :: IO ()
main = do
    putStrLn $ "Aire du cercle (r=5) : " ++ show (area circleExample)
    putStrLn $ "Aire du rectangle (10x5) : " ++ show (area rectangleExample)
```

---

**Explication**

* `data Shape = Circle Float | Rectangle Float Float` : type algébrique avec deux constructeurs, un pour le cercle et un pour le rectangle.
* `area (Circle r) = pi * r * r` : calcul de l’aire du cercle.
* `area (Rectangle l w) = l * w` : calcul de l’aire du rectangle.
* `circleExample` et `rectangleExample` : exemples de formes pour tester la fonction.
* `main` : affiche les résultats à l’exécution.

---

**Exemple de résultat à l’exécution**

```
Aire du cercle (r=5) : 78.53982
Aire du rectangle (10x5) : 50.0
```
