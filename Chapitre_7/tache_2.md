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

---

```haskell
-- Main.hs

-- Définition de la classe WeAccept
class WeAccept a where
    accept :: a -> Bool

-- Exemple de types
data Cardano = Cardano deriving (Show)
data Cash = Cash Int deriving (Show)
data Country = Country String deriving (Show)

-- Instances de WeAccept pour chaque type
instance WeAccept Cardano where
    accept _ = True

instance WeAccept Cash where
    accept (Cash amount) = amount >= 100

instance WeAccept Country where
    accept (Country name) = name == "Burkina Faso"

-- Fonction fancyFunction
-- On ajoute Show a pour pouvoir utiliser show
fancyFunction :: (WeAccept a, Show a) => a -> String
fancyFunction x =
    if accept x
        then "Accepted: " ++ show x
        else "Rejected: " ++ show x

-- Fonction principale pour tester
main :: IO ()
main = do
    putStrLn $ fancyFunction Cardano
    putStrLn $ fancyFunction (Cash 50)
    putStrLn $ fancyFunction (Cash 150)
    putStrLn $ fancyFunction (Country "France")
    putStrLn $ fancyFunction (Country "Burkina Faso")
```

---

### **Explication**

1. **Classe `WeAccept`** :
   Définit la méthode `accept` qui retourne `True` si l’élément est accepté.

2. **Types `Cardano`, `Cash`, `Country`** :
   Simulent différents objets que l’on peut accepter ou rejeter.

3. **Instances de `WeAccept`** :

   * `Cardano` est toujours accepté.
   * `Cash` est accepté si le montant est ≥ 100.
   * `Country` est accepté seulement si le nom est `"Burkina Faso"`.

4. **`fancyFunction`** :
   Combine `accept` et `show` pour afficher le résultat.

   * On ajoute `(Show a)` pour que Haskell sache comment convertir `x` en chaîne.

5. **`main`** :
   Teste la fonction sur différents exemples et affiche le résultat dans le terminal.

---

### **Résultat attendu à l’exécution**

```
Accepted: Cardano
Rejected: Cash 50
Accepted: Cash 150
Rejected: Country "France"
Accepted: Country "Burkina Faso"
```

---
