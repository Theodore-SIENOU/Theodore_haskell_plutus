**HC8T9 - Tâche 9 : Type enregistrement Transaction et fonction associée**

**Sujet**

* Définir un type `Transaction` avec les champs :

  * `from :: Address`
  * `to :: Address`
  * `amount :: Value`
  * `transactionId :: String`
* Définir une fonction `createTransaction :: Address -> Address -> Value -> String` qui crée une transaction et retourne son ID.

---

**Correction complète**

```haskell
-- Main.hs

-- Synonymes de type
type Address = String
type Value = Int

-- Type enregistrement Transaction
data Transaction = Transaction
  { from :: Address
  , to :: Address
  , amount :: Value
  , transactionId :: String
  } deriving (Show)

-- Fonction pour créer une transaction et retourner son ID
createTransaction :: Address -> Address -> Value -> String
createTransaction sender receiver val =
  let txId = "TX" ++ show (length sender + length receiver + val) -- exemple simple d'ID
      tx = Transaction { from = sender, to = receiver, amount = val, transactionId = txId }
  in transactionId tx

-- Exemple d'utilisation
main :: IO ()
main = do
    let txId1 = createTransaction "Alice" "Bob" 100
    let txId2 = createTransaction "Carol" "Dave" 250
    putStrLn $ "Transaction 1 ID: " ++ txId1
    putStrLn $ "Transaction 2 ID: " ++ txId2
```

---

**Explication**

* `data Transaction = Transaction { ... }` crée un type enregistrement avec des champs nommés.
* `createTransaction` construit une instance de `Transaction` et retourne son `transactionId`.
* Ici, l’ID est généré simplement comme `"TX" ++ show (longueur totale des noms + montant)` pour l’exemple.
* `main` montre comment créer plusieurs transactions et afficher leurs IDs.

---

**Exemple de résultat à l’exécution**

```
Transaction 1 ID: TX108
Transaction 2 ID: TX259
```
