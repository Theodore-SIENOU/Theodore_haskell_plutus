### **HC10T1 - Tâche 1 : Classe de type ShowSimple**

#### **Sujet**

> Définir une nouvelle classe de type `ShowSimple` qui exige une fonction `showSimple :: a -> String` pour une conversion simple en chaîne de caractères.
> Implémenter une instance pour le type `PaymentMethod`.

---

###  **Correction complète**

```haskell
-- Fichier : Main.hs

-- Type PaymentMethod défini précédemment
data PaymentMethod = Cash | Card | Cryptocurrency
    deriving (Eq, Show)

-- Définition de la classe de type ShowSimple
class ShowSimple a where
    showSimple :: a -> String

-- Instance de ShowSimple pour PaymentMethod
instance ShowSimple PaymentMethod where
    showSimple Cash = "Cash"
    showSimple Card = "Card"
    showSimple Cryptocurrency = "Cryptocurrency"

-- Fonction principale pour tester
main :: IO ()
main = do
    let pm1 = Cash
    let pm2 = Card
    let pm3 = Cryptocurrency
    putStrLn $ "Méthode 1 : " ++ showSimple pm1
    putStrLn $ "Méthode 2 : " ++ showSimple pm2
    putStrLn $ "Méthode 3 : " ++ showSimple pm3
```

---

###  **Explication**

* `class ShowSimple a` définit une interface qui exige une fonction `showSimple` pour convertir un type `a` en `String`.
* L’instance pour `PaymentMethod` précise comment chaque constructeur (`Cash`, `Card`, `Cryptocurrency`) est converti en texte simple.
* `putStrLn $ showSimple pm` permet d’afficher la version simple de chaque méthode de paiement.

---

### **Résultat à l’exécution**

```
Méthode 1 : Cash
Méthode 2 : Card
Méthode 3 : Cryptocurrency
```

---
