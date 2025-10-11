### **HC9T1 - Tâche 1 : Synonyme de type paramétrique**

#### **Sujet**

* Créer un **synonyme de type paramétrique** appelé `Entity a`
* Ce type doit représenter différents types d’entités avec des adresses.

---

###  **Correction complète**

```haskell
-- Main.hs

-- Définition d’un synonyme de type paramétrique
type Entity a = (a, String)
-- Ici, 'a' représente le type de l’entité (par exemple un identifiant ou un nom)
-- et 'String' représente son adresse.

-- Exemple d’entités avec différents types
personEntity :: Entity String
personEntity = ("Alice", "123 Main Street")

companyEntity :: Entity Int
companyEntity = (101, "456 Business Avenue")

-- Fonction d’affichage générique
showEntity :: Show a => Entity a -> String
showEntity (idOrName, address) =
    "Entity: " ++ show idOrName ++ " | Address: " ++ address

-- Fonction principale
main :: IO ()
main = do
    putStrLn (showEntity personEntity)
    putStrLn (showEntity companyEntity)
```

---

###  **Explication**

* `type Entity a = (a, String)`
  → C’est un **synonyme de type paramétrique** : `a` peut être remplacé par n’importe quel type (par exemple `Int`, `String`, etc.).
  Le tuple `(a, String)` représente une entité avec :

  * un identifiant ou un nom de type `a`
  * une adresse de type `String`

* `showEntity` utilise la contrainte `Show a` pour pouvoir afficher la partie générique.

---

### **Exemple de sortie**

```
Entity: "Alice" | Address: 123 Main Street
Entity: 101 | Address: 456 Business Avenue
```

---
