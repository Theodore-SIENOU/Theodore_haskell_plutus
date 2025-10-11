### **HC7T8 – Parser une valeur avec `Read` (sécurisé)**

**Sujet :**
Écrire une fonction `parseShape` qui prend une `String` et retourne `Maybe Shape`. Elle doit retourner `Nothing` en cas d’entrée invalide.

---

###  **Correction complète**

```haskell
import Text.Read (readMaybe)

-- Définition du type Shape
data Shape = Circle Double | Rectangle Double Double
    deriving (Show, Read)

-- Fonction parseShape sécurisée
parseShape :: String -> Maybe Shape
parseShape s = readMaybe s

-- Fonction principale pour tester
main :: IO ()
main = do
    let circleStr = "Circle 5.0"
    let rectStr = "Rectangle 10.0 5.0"
    let invalidStr = "Triangle 3.0 4.0"

    print $ parseShape circleStr     -- Just (Circle 5.0)
    print $ parseShape rectStr       -- Just (Rectangle 10.0 5.0)
    print $ parseShape invalidStr    -- Nothing
```

---

###  **Explication**

* `readMaybe :: Read a => String -> Maybe a` tente de parser une chaîne en type `a`.

  * Si la chaîne est correcte → `Just valeur`.
  * Sinon → `Nothing`.
* `parseShape` utilise donc `readMaybe` pour transformer une `String` en `Maybe Shape` sans générer d’erreur.
* Les constructeurs `Circle` et `Rectangle` doivent être exactement écrits comme dans la définition du type (`majuscule` et espaces corrects).

---

###  **Résultat attendu à l’exécution**

```
Just (Circle 5.0)
Just (Rectangle 10.0 5.0)
Nothing
```
