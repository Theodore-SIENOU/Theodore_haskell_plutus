##  HC5T5 – Tâche 5 : Application partielle

###  Objectif

Créer une fonction `multiplyByFive` qui :

1. Utilise **l’application partielle** pour multiplier un nombre par 5.
2. Évite d’écrire explicitement le paramètre.
3. Peut être utilisée sur n’importe quel entier ou nombre compatible (`Num a => a`).


###  Exemple corrigé avec application partielle

```haskell
-- Fichier : Main.hs

-- Version avec application partielle
multiplyByFive :: Num a => a -> a
multiplyByFive = (* 5)

-- Programme principal pour tester
main :: IO ()
main = do
    print $ multiplyByFive 2    -- 10
    print $ multiplyByFive 7    -- 35
    print $ multiplyByFive 0    -- 0
```


###  Explications

* `(* 5)` = fonction qui attend un argument et le multiplie par 5.
* `multiplyByFive = (* 5)` = **application partielle**, on n’écrit pas le paramètre explicitement.
* Fonction **générique** : type `Num a => a -> a`, fonctionne avec `Int`, `Double`, etc.
* Exemple : `multiplyByFive 2` → `2 * 5 = 10`.


###  Résultats attendus

```
10
35
0
```
