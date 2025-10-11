### **HC9T5 - Tâche 5 : Type de données paramétrique avec syntaxe d’enregistrement**

#### **Sujet**

> Définir un type de données paramétrique `Shape a` avec les constructeurs `Circle` et `Rectangle`,
> contenant chacun un champ `color` de type `a`.

---

###  **Correction complète**

```haskell
-- Fichier : Main.hs

-- Définition d’un type paramétrique Shape avec syntaxe d’enregistrement
data Shape a
    = Circle { radius :: Float, color :: a }
    | Rectangle { width :: Float, height :: Float, color :: a }
    deriving (Show)

-- Exemples de formes
circle1 :: Shape String
circle1 = Circle { radius = 5.0, color = "Red" }

rectangle1 :: Shape String
rectangle1 = Rectangle { width = 10.0, height = 6.0, color = "Blue" }

main :: IO ()
main = do
    print circle1
    print rectangle1
```

---

###  **Explication**

* `Shape a` est un **type paramétrique** :
  le type `a` représente le type de la couleur (ex. `String`, `Int`, etc.).
* `Circle` et `Rectangle` utilisent la **syntaxe d’enregistrement** pour nommer les champs.
* Grâce à `deriving (Show)`, on peut afficher directement les formes avec `print`.

---

### **Résultat à l’exécution**

```
Circle {radius = 5.0, color = "Red"}
Rectangle {width = 10.0, height = 6.0, color = "Blue"}
```

---
