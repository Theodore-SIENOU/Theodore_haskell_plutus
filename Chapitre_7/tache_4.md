### **HC7T4 – Type personnalisé avec Show et Read**

**Sujet :**
Définir un type de données `Shape` avec les constructeurs :

* `Circle Double`
* `Rectangle Double Double`

Puis implémenter **manuellement** les instances `Show` et `Read` pour ce type.

---

###  **Correction complète**

```haskell
-- Définition du type Shape
data Shape = Circle Double
           | Rectangle Double Double

-- Implémentation manuelle de Show
instance Show Shape where
    show (Circle r) = "Circle (radius = " ++ show r ++ ")"
    show (Rectangle w h) = "Rectangle (width = " ++ show w ++ ", height = " ++ show h ++ ")"

-- Implémentation manuelle de Read
instance Read Shape where
    readsPrec _ input =
        case words input of
            ["Circle", r] ->
                [(Circle (read r), "")]
            ["Rectangle", w, h] ->
                [(Rectangle (read w) (read h), "")]
            _ -> []

-- Fonction principale pour tester
main :: IO ()
main = do
    -- Création de formes
    let c = Circle 5.0
    let r = Rectangle 10.0 4.0

    -- Affichage via Show
    putStrLn ("Affichage du cercle : " ++ show c)
    putStrLn ("Affichage du rectangle : " ++ show r)

    -- Lecture (Read) depuis une chaîne
    let c2 = read "Circle 7.5" :: Shape
    let r2 = read "Rectangle 3.0 6.0" :: Shape

    putStrLn ("Lecture du cercle : " ++ show c2)
    putStrLn ("Lecture du rectangle : " ++ show r2)
```

---

###  **Explication**

* `Show` permet de **convertir** une valeur en texte (`String`).
* `Read` fait l’inverse : **interprète** une chaîne de texte pour recréer la valeur.
* On utilise `readsPrec` pour définir comment le texte doit être lu.

---

###  **Résultat attendu à l’exécution**

```
Affichage du cercle : Circle (radius = 5.0)
Affichage du rectangle : Rectangle (width = 10.0, height = 4.0)
Lecture du cercle : Circle (radius = 7.5)
Lecture du rectangle : Rectangle (width = 3.0, height = 6.0)
```

---
