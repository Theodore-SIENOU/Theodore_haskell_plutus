##  HC5T6 – Tâche 6 : Composition de fonctions

###  Objectif

Créer une fonction qui :

1. Prend une **liste de nombres** en entrée.
2. Calcule le **carré** de chaque élément (`map (^2)`).
3. Filtre les résultats pour **ne garder que les nombres pairs** (`filter even`).
4. Utilise la **composition de fonctions** `(.)` pour combiner les étapes au lieu d’appeler les fonctions séparément.

---

###  Exemple corrigé avec composition `(.)`

```haskell
-- Fichier : Main.hs

-- Fonction qui compose map et filter
carresPairs :: [Int] -> [Int]
carresPairs = filter even . map (^2)

-- Programme principal pour tester
main :: IO ()
main = do
    print $ carresPairs [1..10]
    print $ carresPairs [3,4,5,6]
```


###  Explications

* `map (^2)` = applique le carré à chaque élément de la liste.
* `filter even` = garde uniquement les **nombres pairs**.
* `(filter even . map (^2))` = composition de fonctions :

  * d’abord `map (^2)` est appliqué,
  * ensuite `filter even` est appliqué au résultat.
* Équivaut à écrire :

```haskell
carresPairs xs = filter even (map (^2) xs)
```

###  Résultats attendus

```
[4,16,36,64,100]
[16,36]
```
