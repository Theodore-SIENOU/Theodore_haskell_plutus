### **HC9T2 - Tâche 2 : Type de données paramétrique**

#### **Énoncé**

> Créer un type de données `Box a` avec deux constructeurs :
>
> * `Empty` → représente une boîte vide
> * `Has a` → représente une boîte qui contient une valeur

---

###  **Correction complète**

```haskell
-- Main.hs

-- Définition d’un type de données paramétrique
data Box a = Empty | Has a
    deriving (Show)

-- Exemple d’utilisation
box1 :: Box Int
box1 = Has 42

box2 :: Box String
box2 = Has "Hello, world!"

box3 :: Box a
box3 = Empty

-- Fonction pour vérifier si une boîte est vide
isEmpty :: Box a -> Bool
isEmpty Empty = True
isEmpty _     = False

-- Fonction pour extraire le contenu (avec valeur par défaut)
getValue :: Box a -> a -> a
getValue Empty defaultVal = defaultVal
getValue (Has x) _        = x

-- Fonction principale pour tester
main :: IO ()
main = do
    print box1
    print box2
    print (isEmpty box3)
    print (getValue box1 0)
    print (getValue box3 99)
```

---

###  **Explication**

* `data Box a = Empty | Has a`
  → crée un **type de données paramétrique** :
  le type `a` peut être remplacé par n’importe quel type (`Int`, `String`, etc.).

* `Empty` : représente une boîte vide

* `Has a` : représente une boîte contenant une valeur de type `a`

* La dérivation `deriving (Show)` permet d’afficher les valeurs dans le terminal.

---

### **Exemple de sortie**

```
Has 42
Has "Hello, world!"
True
42
99
```

---
