**HC8T6 - Tâche 6 : Syntaxe d’enregistrement pour variantes Shape**

**Sujet**

* Définir un type `Shape` avec la syntaxe d’enregistrement incluant :

  * Pour les cercles : `center :: (Float, Float)`, `color :: String`, `radius :: Float`
  * Pour les rectangles : `width :: Float`, `height :: Float`, `color :: String`
* Créer une instance de `Shape` pour un cercle et un rectangle.

---

**Correction complète**

```haskell
-- Main.hs

-- Définition du type Shape avec syntaxe d'enregistrement pour les variantes
data Shape
    = Circle { center :: (Float, Float), color :: String, radius :: Float }
    | Rectangle { width :: Float, height :: Float, color :: String }
    deriving (Show, Eq)

-- Création d'un cercle
myCircle :: Shape
myCircle = Circle { center = (0.0, 0.0), color = "Red", radius = 5.0 }

-- Création d'un rectangle
myRectangle :: Shape
myRectangle = Rectangle { width = 10.0, height = 5.0, color = "Blue" }

-- Fonction principale pour tester
main :: IO ()
main = do
    putStrLn $ "Cercle : " ++ show myCircle
    putStrLn $ "Rectangle : " ++ show myRectangle
```

---

**Explication**

* `data Shape = Circle { ... } | Rectangle { ... }` : définit un type avec deux variantes et champs nommés pour chaque variante.
* `myCircle` : instance de `Circle` avec centre, couleur et rayon.
* `myRectangle` : instance de `Rectangle` avec largeur, hauteur et couleur.
* `deriving (Show, Eq)` : permet d’afficher les instances et de les comparer facilement.

---

**Exemple de résultat à l’exécution**

```
Cercle : Circle {center = (0.0,0.0), color = "Red", radius = 5.0}
Rectangle : Rectangle {width = 10.0, height = 5.0, color = "Blue"}
```
