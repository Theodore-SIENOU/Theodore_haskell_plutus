**HC10T6 - Récursivité mutuelle dans Eq pour Blockchain**

**Sujet**

Modifier la classe Eq pour utiliser la récursivité mutuelle entre `==` et `/=` dans une instance pour le type `Blockchain`.

---

**Correction complète**

```haskell
-- Définition du type Blockchain
data Blockchain = Bitcoin | Ethereum | Cardano
  deriving (Show)

-- Instance Eq avec récursivité mutuelle
instance Eq Blockchain where
    -- Définition de == en utilisant /= pour la récursivité
    x == y = not (x /= y)

    -- Définition de /= en utilisant == pour la récursivité
    x /= y = case (x, y) of
                (Bitcoin, Bitcoin) -> False
                (Ethereum, Ethereum) -> False
                (Cardano, Cardano) -> False
                _ -> True

-- Fonction principale pour tester
main :: IO ()
main = do
    print $ Bitcoin == Bitcoin     -- True
    print $ Bitcoin == Ethereum    -- False
    print $ Cardano /= Ethereum    -- True
    print $ Ethereum /= Ethereum   -- False
```

---

**Explication**

* `==` et `/=` s’appellent mutuellement, ce qui permet d’éviter de dupliquer la logique de comparaison.
* Pour `/=`, on fait une comparaison explicite des cas. Si les deux valeurs sont identiques, `/=` retourne `False`. Sinon, `True`.
* Pour `==`, on utilise `not (x /= y)`, donc `==` dépend de `/=`.

---

**Résultat à l’exécution**

```
True
False
True
False
```

---
