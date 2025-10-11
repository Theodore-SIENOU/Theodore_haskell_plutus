### **HC7T9 – Classe de type avec plusieurs instances**

**Sujet :**
Créer une classe de type `Describable` avec une méthode `describe`.
L’implémenter pour `Bool` et `Shape`.

---

###  **Correction complète**

```haskell
-- Définition du type Shape
data Shape = Circle Double | Rectangle Double Double
    deriving (Show, Read)

-- Définition de la classe de type Describable
class Describable a where
    describe :: a -> String

-- Instance pour Bool
instance Describable Bool where
    describe True  = "This is True"
    describe False = "This is False"

-- Instance pour Shape
instance Describable Shape where
    describe (Circle r)      = "A circle with radius " ++ show r
    describe (Rectangle w h) = "A rectangle with width " ++ show w ++ " and height " ++ show h

-- Fonction principale pour tester
main :: IO ()
main = do
    print $ describe True                     -- "This is True"
    print $ describe False                    -- "This is False"
    print $ describe (Circle 5.0)             -- "A circle with radius 5.0"
    print $ describe (Rectangle 10.0 5.0)    -- "A rectangle with width 10.0 and height 5.0"
```

---

###  **Explication**

* `class Describable a where describe :: a -> String` définit une classe de type générique avec une méthode `describe`.
* `instance Describable Bool` fournit une description textuelle pour les valeurs `True` et `False`.
* `instance Describable Shape` décrit les formes avec leurs dimensions.
* Cette approche permet d’utiliser `describe` pour différents types sans dupliquer du code.

---

###  **Résultat attendu à l’exécution**

```
"This is True"
"This is False"
"A circle with radius 5.0"
"A rectangle with width 10.0 and height 5.0"
```
