**HC11T9 - Tâche 9 : Type `Length` avec unités**

**Sujet**

Créer un type `Length` avec deux unités (`M` pour mètres et `Km` pour kilomètres).

* Dériver `Eq` pour les comparaisons d’égalité.
* Implémenter manuellement `Ord` pour permettre des comparaisons correctes entre mètres et kilomètres.

---

**Correction complète**

```haskell
-- Main.hs

-- Définition du type Length
data Length = M Double | Km Double
    deriving (Show, Eq)

-- Instance Ord pour comparer correctement mètres et kilomètres
instance Ord Length where
    compare (M x) (M y)     = compare x y
    compare (Km x) (Km y)   = compare x y
    compare (M x) (Km y)    = compare x (y * 1000)
    compare (Km x) (M y)    = compare (x * 1000) y

-- Fonction main pour tester
main :: IO ()
main = do
    let l1 = M 500
        l2 = Km 1
        l3 = Km 2

    print $ l1 == M 500        -- True
    print $ l1 < l2            -- True (500 m < 1000 m)
    print $ l3 > l2            -- True (2000 m > 1000 m)
    print $ M 1500 >= Km 1     -- True (1500 m >= 1000 m)
```

---

**Explication**

* `data Length = M Double | Km Double` :

  * Type représentant une longueur avec deux unités.
* `deriving (Show, Eq)` :

  * `Show` pour affichage.
  * `Eq` pour l’égalité (`==`, `/=`).
* `instance Ord Length` :

  * `compare` convertit les unités si nécessaire afin que la comparaison soit correcte.
  * Exemple : `M 500 < Km 1` → `500 < 1000` → `True`.

---

**Exemple de résultat à l’exécution**

```
True
True
True
True
```

---
