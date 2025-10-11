### **HC7T1 – Implémenter une instance Eq pour un type personnalisé**

**Sujet :**

* Définir un type de données `Color` représentant `Red`, `Green` et `Blue`.
* Implémenter la classe de type `Eq` afin que deux couleurs du même type soient considérées égales.

---

###  **Correction complète**

```haskell
-- Définition du type Color
data Color = Red | Green | Blue

-- Implémentation manuelle de la classe Eq
instance Eq Color where
    Red   == Red   = True
    Green == Green = True
    Blue  == Blue  = True
    _     == _     = False

-- Programme principal pour tester
main :: IO ()
main = do
    print (Red == Red)     -- True
    print (Red == Blue)    -- False
    print (Green == Green) -- True
```

---

###  **Explication**

* Le type `Color` est une **énumération simple** avec trois constructeurs : `Red`, `Green` et `Blue`.
* En implémentant `instance Eq Color where ...`, on définit comment comparer deux couleurs :

  * Si les deux valeurs ont le **même constructeur**, elles sont égales.
  * Sinon, elles sont différentes.
* Le motif `_ == _ = False` capture tous les autres cas.

---

###  **Résultat attendu à l’exécution**

```
True
False
True
```

---
