### **HC10T7 – Classe de type Convertible**

**Sujet**
Créer une classe de type `Convertible` avec `convert :: a -> b`.
L’implémenter pour la conversion de `PaymentMethod` en `String`.

---

###  **Correction complète**

```haskell
-- Définition du type PaymentMethod
data PaymentMethod = Cash | CreditCard | Crypto
  deriving (Show)

-- Définition de la classe de type Convertible
class Convertible a b where
    convert :: a -> b

-- Instance de Convertible pour PaymentMethod -> String
instance Convertible PaymentMethod String where
    convert Cash       = "Cash payment"
    convert CreditCard = "Credit card payment"
    convert Crypto     = "Cryptocurrency payment"

-- Fonction principale pour tester
main :: IO ()
main = do
    putStrLn (convert Cash)
    putStrLn (convert CreditCard)
    putStrLn (convert Crypto)
```

---

###  **Explication**

* `class Convertible a b` définit une **classe paramétrique à deux types** :
  le type source `a` et le type cible `b`.
* L’instance `Convertible PaymentMethod String` décrit **comment convertir** un mode de paiement en texte.
* Chaque constructeur de `PaymentMethod` est converti en une chaîne descriptive.

---

###  **Résultat à l’exécution**

```
Cash payment
Credit card payment
Cryptocurrency payment
```

---
