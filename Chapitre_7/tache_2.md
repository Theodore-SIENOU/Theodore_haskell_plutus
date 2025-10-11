### **HC7T2 – Implémenter une instance Ord pour un type personnalisé**

**Sujet :**
Utiliser le type `Color` défini précédemment (`Red`, `Green`, `Blue`) et implémenter la classe `Ord` pour que :
 `Red < Green < Blue`.

---

###  **Correction complète**

```haskell
-- Définition du type Color
data Color = Red | Green | Blue
    deriving (Eq, Show)  -- On dérive Eq et Show pour pouvoir comparer et afficher

-- Implémentation manuelle de la classe Ord
instance Ord Color where
    compare Red Green  = LT
    compare Red Blue   = LT
    compare Green Blue = LT
    compare a b
        | a == b    = EQ
        | otherwise = GT

-- Programme principal pour tester
main :: IO ()
main = do
    print (Red < Green)    -- True
    print (Green < Blue)   -- True
    print (Blue > Red)     -- True
    print (compare Red Blue)  -- LT
    print (compare Blue Green) -- GT
```

---

###  **Explication**

* On dérive `Eq` et `Show` pour rendre le type comparable et affichable.
* L’instance `Ord` définit **l’ordre logique** entre les couleurs :

  * `Red` est plus petit que `Green` et `Blue`.
  * `Green` est plus petit que `Blue`.
* Si deux couleurs sont identiques → `EQ`, sinon → `GT`.

---

###  **Résultat attendu à l’exécution**

```
True
True
True
LT
GT
```

---
