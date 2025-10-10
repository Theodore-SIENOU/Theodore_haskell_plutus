# **HC11T2 - Fonction `fancyFunction` pour `WeAccept`**

### **Sujet**

Implémenter la fonction `fancyFunction` pour la classe `WeAccept` et la tester avec différents types comme `Cardano`, `Cash` et `Country`.

Supposons que nous ayons les types suivants :

```haskell
data Cardano = Cardano Int deriving Show
data Cash    = Cash Int deriving Show
data Country = Country String deriving Show
```

On a déjà la classe :

```haskell
class WeAccept a where
    accept :: a -> Bool
```

On veut :

* Définir une fonction `fancyFunction :: WeAccept a => a -> String` qui retourne un message selon que l’objet est accepté ou non.
* Créer des instances `WeAccept` pour `Cardano`, `Cash` et `Country`.

---

### **Correction complète**

```haskell
-- Définition des types
data Cardano = Cardano Int deriving Show
data Cash    = Cash Int deriving Show
data Country = Country String deriving Show

-- Classe WeAccept
class WeAccept a where
    accept :: a -> Bool

-- Instances WeAccept
instance WeAccept Cardano where
    accept (Cardano amount) = amount > 0

instance WeAccept Cash where
    accept (Cash amount) = amount >= 100

instance WeAccept Country where
    accept (Country name) = name `elem` ["France", "Burkina Faso", "USA"]

-- Fonction fancyFunction
fancyFunction :: WeAccept a => a -> String
fancyFunction x =
    if accept x
        then "Accepted: " ++ show x
        else "Rejected: " ++ show x

-- Fonction principale : teste fancyFunction
main :: IO ()
main = do
    let c1 = Cardano 50
        c2 = Cardano 0
        cash1 = Cash 200
        cash2 = Cash 50
        country1 = Country "France"
        country2 = Country "Mars"
    
    putStrLn $ fancyFunction c1
    putStrLn $ fancyFunction c2
    putStrLn $ fancyFunction cash1
    putStrLn $ fancyFunction cash2
    putStrLn $ fancyFunction country1
    putStrLn $ fancyFunction country2
```

---

### **Explication**

* **Instances `WeAccept`** : chaque type a sa propre règle d’acceptation.

  * `Cardano` est accepté si son montant > 0.
  * `Cash` est accepté si le montant ≥ 100.
  * `Country` est accepté si le pays est dans une liste autorisée.
* **`fancyFunction`** : prend n’importe quel type `WeAccept` et retourne un message `"Accepted"` ou `"Rejected"` avec la valeur affichée.
* **`main`** : teste `fancyFunction` avec plusieurs valeurs pour chaque type.

---

### **Résultat à l’exécution**

```
Accepted: Cardano 50
Rejected: Cardano 0
Accepted: Cash 200
Rejected: Cash 50
Accepted: Country "France"
Rejected: Country "Mars"
```
