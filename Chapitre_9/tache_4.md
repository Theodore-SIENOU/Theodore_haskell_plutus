### **HC9T4 - Tâche 4 : Extraire une valeur d’une Box**

#### **Sujet**

> Créer une fonction `extract` qui prend une valeur par défaut et une `Box a`.
> Elle retourne la valeur à l’intérieur de la boîte, ou la valeur par défaut si la boîte est vide.

---

###  **Correction complète**

```haskell
-- Fichier : Main.hs

-- Définition du type paramétrique Box
data Box a = Empty | Has a
    deriving (Show)

-- Fonction extract : retourne la valeur de la Box ou une valeur par défaut
extract :: a -> Box a -> a
extract def Empty    = def
extract _   (Has x)  = x

-- Exemples de test
box1 :: Box Int
box1 = Has 42

box2 :: Box Int
box2 = Empty

main :: IO ()
main = do
    print (extract 0 box1)  -- Résultat attendu : 42
    print (extract 0 box2)  -- Résultat attendu : 0
```

---

###  **Explication**

* `extract` prend deux arguments :

  * une **valeur par défaut** (`def`)
  * une **boîte** (`Box a`)
* Elle agit comme une **fonction de déballage sûre** :

  * Si la boîte est `Empty`, on retourne la valeur par défaut.
  * Si la boîte contient une valeur (`Has x`), on retourne `x`.

---

### **Résultat à l’exécution**

```
42
0
```

---
