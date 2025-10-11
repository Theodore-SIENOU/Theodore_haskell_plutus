### HC10T4 - Instance Eq pour Box

**Sujet**

Créer un type paramétrique `Box a` pouvant contenir une valeur ou être vide, puis en faire une instance de `Eq`. Tester l’égalité entre différentes boîtes.

---

**Correction complète**

```haskell
-- Fichier : Main.hs

-- Définition du type paramétrique Box
data Box a = Empty | Has a deriving (Show)

-- Instance Eq pour Box
instance (Eq a) => Eq (Box a) where
    Empty == Empty = True
    Has x == Has y = x == y
    _ == _         = False

-- Fonction principale pour tester
main :: IO ()
main = do
    let box1 = Has 10
        box2 = Has 10
        box3 = Has 20
        boxEmpty = Empty :: Box Int  -- Annotation de type pour lever l'ambiguïté
    print $ box1 == box2               -- True
    print $ box1 == box3               -- False
    print $ box1 == boxEmpty           -- False
    print $ boxEmpty == (Empty :: Box Int) -- True
```

---

**Explication**

* `data Box a = Empty | Has a` : définit une boîte paramétrique qui peut être vide (`Empty`) ou contenir une valeur (`Has a`).
* `instance (Eq a) => Eq (Box a)` : permet de comparer deux `Box a` si `a` est lui-même `Eq`.
* Les cas :

  * `Empty == Empty = True` : deux boîtes vides sont égales.
  * `Has x == Has y = x == y` : deux boîtes non vides sont égales si leurs contenus sont égaux.
  * `_ == _ = False` : tous les autres cas (vide vs non vide) sont différents.
* L’annotation `Empty :: Box Int` est nécessaire pour lever l’ambiguïté de type que Haskell ne peut pas deviner seul.

---

**Résultat à l’exécution**

```
True
False
False
True
```

---
