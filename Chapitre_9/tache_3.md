### **HC9T3 - Tâche 3 : Fonction addN**

#### **Énoncé**

> Créer une fonction `addN` qui prend un nombre et une `Box a`.
> Si la boîte contient un nombre (`Has x`), on additionne ce nombre à la valeur donnée.

---

###  **Correction complète**

```haskell
-- Main.hs

-- Définition du type paramétrique Box
data Box a = Empty | Has a
    deriving (Show)

-- Fonction addN : ajoute n à la valeur dans la Box (si elle existe)
addN :: Num a => a -> Box a -> Box a
addN n Empty    = Empty
addN n (Has x)  = Has (x + n)

-- Exemples de test
box1 :: Box Int
box1 = Has 10

box2 :: Box Int
box2 = Empty

main :: IO ()
main = do
    print (addN 5 box1)   -- Résultat attendu : Has 15
    print (addN 3 box2)   -- Résultat attendu : Empty
```

---

###  **Explication**

* Le type `Box a` peut contenir une valeur (`Has a`) ou être vide (`Empty`).
* `addN` vérifie le contenu :

  * Si la boîte est vide → elle reste `Empty`
  * Si elle contient une valeur `x` → on renvoie `Has (x + n)`
* La contrainte de type `Num a =>` est nécessaire, car on utilise l’opérateur `+`.

---

### **Sortie attendue**

```
Has 15
Empty
```

---
