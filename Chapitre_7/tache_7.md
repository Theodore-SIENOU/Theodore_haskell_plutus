**HC11T7 - Tâche 7 : Instance `Ord` pour `Box`**

**Sujet**

Implémenter l’instance `Ord` pour le type `Box` afin de pouvoir comparer deux boîtes. La comparaison doit se baser sur la valeur contenue dans la boîte.

---

**Correction complète**

```haskell
-- Main.hs

-- Définition du type Box
data Box a = Box a deriving (Show, Eq)

-- Instance Ord pour Box
instance Ord a => Ord (Box a) where
    compare (Box x) (Box y) = compare x y

-- Fonction main pour tester
main :: IO ()
main = do
    let box1 = Box 5
        box2 = Box 10
        box3 = Box 5

    print $ box1 < box2    -- True
    print $ box2 > box1    -- True
    print $ box1 == box3   -- True
    print $ box1 >= box2   -- False
```

---

**Explication**

* `data Box a = Box a` :

  * Déclare un type générique `Box` contenant une valeur de type `a`.
* `instance Ord a => Ord (Box a)` :

  * Déclare que pour pouvoir comparer des `Box a`, le type `a` doit déjà être `Ord`.
* `compare (Box x) (Box y) = compare x y` :

  * Délègue la comparaison à la valeur contenue dans la boîte.
* Les autres opérateurs (`<`, `>`, `<=`, `>=`) sont dérivés automatiquement de `compare`.

---

**Exemple de résultat à l’exécution**

```
True
True
True
False
```

---
