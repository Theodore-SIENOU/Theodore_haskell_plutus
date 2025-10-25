### **HC12T7 – Calculer l’aire d’un cercle**

**Sujet :**
Créer une fonction `calculateCircleArea` qui calcule l’aire d’un cercle à partir de son rayon.
La fonction `main` doit démontrer son utilisation.

---

###  **Correction complète**

```haskell
-- Définition de la fonction pour calculer l’aire d’un cercle
calculateCircleArea :: Floating a => a -> a
calculateCircleArea r = pi * r * r

-- Fonction principale pour tester
main :: IO ()
main = do
    putStrLn "Entrez le rayon du cercle :"
    input <- getLine
    let rayon = read input :: Double
    let aire = calculateCircleArea rayon
    putStrLn ("L’aire du cercle est : " ++ show aire)
```

---

###  **Explication**

* `calculateCircleArea` utilise la formule **A = π × r²**.
* La contrainte `Floating a` permet d’utiliser des nombres à virgule (`Float`, `Double`, etc.).
* `read input :: Double` convertit la chaîne saisie en nombre réel.
* `show aire` convertit le résultat en texte pour l’afficher.

---

###  **Exemple d’exécution**

```
Entrez le rayon du cercle :
5
L’aire du cercle est : 78.53981633974483
```

---

###  **À retenir**

* `pi` est une constante intégrée dans Haskell (≈ 3.141592653589793).
* Tu peux aussi formater le résultat, par exemple en limitant à 2 décimales :

  ```haskell
  putStrLn ("L’aire du cercle est : " ++ show (fromIntegral (round (aire * 100)) / 100))
  ```
