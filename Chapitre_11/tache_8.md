**HC11T8 - Tâche 8 : Dérivation de `Eq` et `Ord` pour `PaymentMethod`**

**Sujet**

Dériver automatiquement les instances `Eq` et `Ord` pour le type `PaymentMethod` afin de pouvoir comparer deux méthodes de paiement.

---

**Correction complète**

```haskell
-- Main.hs

-- Définition du type PaymentMethod
data PaymentMethod = Cash | Card | Crypto
    deriving (Show, Eq, Ord)

-- Fonction main pour tester
main :: IO ()
main = do
    let pm1 = Cash
        pm2 = Card
        pm3 = Crypto

    print $ pm1 == pm2    -- False
    print $ pm2 < pm3     -- True
    print $ pm1 <= pm1    -- True
    print $ pm3 > pm1     -- True
```

---

**Explication**

* `data PaymentMethod = Cash | Card | Crypto` :

  * Déclare un type énuméré représentant différents moyens de paiement.
* `deriving (Show, Eq, Ord)` :

  * `Show` permet d’afficher les valeurs dans `print`.
  * `Eq` permet de comparer l’égalité (`==`, `/=`).
  * `Ord` permet d’utiliser les comparateurs (`<`, `>`, `<=`, `>=`) en utilisant l’ordre de définition des constructeurs (`Cash < Card < Crypto`).

---

**Exemple de résultat à l’exécution**

```
False
True
True
True
```

---
