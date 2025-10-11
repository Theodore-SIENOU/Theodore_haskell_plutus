### **HC7T5 – Fonction utilisant la contrainte `Num`**

**Sujet :**
Écrire une fonction `squareArea` qui calcule l’aire d’un carré à partir de la longueur d’un côté.
La fonction doit fonctionner avec **tout type numérique**.

---

###  **Correction complète**

```haskell
-- Définition de la fonction
squareArea :: Num a => a -> a
squareArea side = side * side

-- Exemple d'utilisation
main :: IO ()
main = do
    print (squareArea 5)       -- Entier
    print (squareArea 3.2)     -- Nombre à virgule
    print (squareArea 10.5)    -- Autre exemple
```

---

###  **Explication**

* La contrainte `Num a =>` signifie que `a` peut être **n’importe quel type numérique** :
  (`Int`, `Integer`, `Float`, `Double`, etc.)
* `side * side` calcule simplement le carré du côté.

---

###  **Résultat attendu à l’exécution**

```
25
10.24
110.25
```

---
