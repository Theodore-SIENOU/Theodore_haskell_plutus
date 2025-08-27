**HC5T5 – Application partielle**.

### Objectif

Créer une fonction multiplyByFive qui utilise l’application partielle
pour multiplier n’importe quel nombre par 5

###  Solution en Haskell

```haskell
multiplyByFive :: Int -> Int
multiplyByFive = (*) 5
```


###  Explication

* `(*)` est l’opérateur de multiplication, de type :

  ```haskell
  (*) :: Num a => a -> a -> a
  ```
* Si on lui applique déjà **un argument (5)**, on obtient une **fonction partielle** :

  ```haskell
  (*) 5 :: Num a => a -> a
  ```

  qui correspond exactement à “multiplier par 5”.


###  Exemple de test

```haskell
main :: IO ()
main = do
    print (multiplyByFive 3)   -- 15
    print (multiplyByFive 10)  -- 50
    print (multiplyByFive 0)   -- 0
```
