**HC5T1 – Utiliser `applyTwice`**

On nous demande d’écrire une fonction qui prend **une fonction** et **un entier**,
puis applique cette fonction **trois fois** à l’entier.

###  Rappel : `applyTwice`

En Haskell, on définit souvent :

```haskell
applyTwice :: (a -> a) -> a -> a
applyTwice f x = f (f x)
```

C’est-à-dire : applique `f` deux fois sur `x`.

###  Solution pour appliquer **trois fois**

On peut définir `applyThrice` à partir de `applyTwice` :

```haskell
applyThrice :: (a -> a) -> a -> a
applyThrice f x = f (applyTwice f x)
```

###  Explication

* `applyTwice f x` applique `f` deux fois : `f (f x)`
* Ensuite on applique encore `f` une fois de plus : `f (f (f x))`

###  Exemple de test

```haskell
main :: IO ()
main = do
    print (applyThrice (+1) 5)   -- 8   (5+1+1+1)
    print (applyThrice (*2) 1)   -- 8   (1*2*2*2)
    print (applyThrice reverse "abc") -- "abc" (car reverse 3 fois remet la chaîne d'origine)
```

###  Résultats attendus

8
8
"abc"
```
