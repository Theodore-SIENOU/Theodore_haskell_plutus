### **HC7T6 – Utiliser `Integral` et `Floating`**

**Sujet :**
Définir une fonction `circleCircumference` qui prend un rayon et retourne la circonférence.
Elle doit fonctionner avec des types **`Integral`** et **`Floating`**.

---

### **Correction complète**

```haskell
-- Définition de la fonction
circleCircumference :: (Integral a, Floating b) => a -> b
circleCircumference r = 2 * pi * fromIntegral r

-- Exemple d'utilisation
main :: IO ()
main = do
    print (circleCircumference 5 :: Double)
    print (circleCircumference 10 :: Float)
```

---

###  **Explication**

* `(Integral a, Floating b) =>` signifie :

  * Le rayon `r` est un **entier** (`Integral` → `Int`, `Integer`, etc.)
  * Le résultat est un **nombre à virgule** (`Floating` → `Float`, `Double`)
* `fromIntegral` convertit le rayon entier vers un type flottant pour pouvoir utiliser `pi`.

---

###  **Résultat attendu à l’exécution**

```
31.41592653589793
62.831856
```

---
