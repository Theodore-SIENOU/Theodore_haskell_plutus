 **HC4T7 – Ignorer des éléments dans une liste**.
 
On doit écrire une fonction qui prend une liste et retourne **seulement le premier et le troisième élément**, en ignorant les autres.

---

##  Solution avec le **pattern matching**

```haskell
-- Fonction qui garde uniquement le 1er et le 3ème élément
firstAndThird :: [a] -> [a]
firstAndThird (x:_:z:_) = [x, z]   -- 1er = x, on ignore le 2ème (_), 3ème = z
firstAndThird (x:_:[])  = [x]      -- Cas où il n’y a pas de 3ème
firstAndThird (x:[])    = [x]      -- Cas où il n’y a qu’un seul élément
firstAndThird []        = []       -- Liste vide
```

---

##  Explication

* `(x:_:z:_)` = prend une liste où :

  * `x` est le **1er élément**
  * `_` = **on ignore** le 2ème
  * `z` est le **3ème élément**
  * `_` après `z` = peu importe le reste
* Les autres cas gèrent quand la liste est trop courte.

---

##  Exemples de test

```haskell
main :: IO ()
main = do
    print (firstAndThird [10,20,30,40,50])  -- [10,30]
    print (firstAndThird [1,2,3])           -- [1,3]
    print (firstAndThird [7,8])             -- [7]
    print (firstAndThird [42])              -- [42]
    print (firstAndThird [])                -- []
```

### Résultats attendus

```
[10,30]
[1,3]
[7]
[42]
[]
```
