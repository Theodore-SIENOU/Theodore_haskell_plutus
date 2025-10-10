**HC8T1 - Tâche 1 : Synonymes de type et fonction de base**

**Sujet**

* Créer un synonyme de type `Address` pour `String` et un synonyme de type `Value` pour `Int`.
* Définir une fonction `generateTx :: Address -> Address -> Value -> String` qui prend deux adresses et une valeur, et retourne une chaîne qui concatène ces informations.

---

**Correction complète**

```haskell
-- Main.hs

-- Synonymes de type
type Address = String
type Value = Int

-- Fonction qui génère une transaction sous forme de chaîne
generateTx :: Address -> Address -> Value -> String
generateTx from to amount =
    "Transaction from " ++ from ++ " to " ++ to ++ " of value " ++ show amount

-- Fonction main pour tester
main :: IO ()
main = do
    let fromAddress = "Alice123"
    let toAddress = "Bob456"
    let amount = 100
    putStrLn $ generateTx fromAddress toAddress amount
```

---

**Explication**

* `type Address = String` : crée un alias `Address` pour `String`.
* `type Value = Int` : crée un alias `Value` pour `Int`.
* `generateTx from to amount` : construit une chaîne en concaténant le texte et les valeurs.
* `show amount` : convertit la valeur entière `amount` en chaîne pour pouvoir la concaténer.

---

**Exemple de résultat à l’exécution**

```
Transaction from Alice123 to Bob456 of value 100
```

---
