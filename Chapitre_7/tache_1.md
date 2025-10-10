# **HC11T1 - Instance `WeAccept` pour Box**

### **Sujet**

Créer une instance `WeAccept` pour le type `Box` et écrire une fonction qui retourne une liste de boîtes acceptées.

Supposons que nous ayons le type suivant :

```haskell
data Box = Box Int String  -- Box poids nom
```

On définit la classe :

```haskell
class WeAccept a where
    accept :: a -> Bool
```

On veut ensuite créer :

* Une instance `WeAccept` pour `Box`.
* Une fonction `acceptedBoxes` qui filtre une liste de `Box` en ne conservant que celles acceptées.

---

### **Correction complète**

```haskell
-- Définition du type Box
data Box = Box Int String deriving Show

-- Classe WeAccept
class WeAccept a where
    accept :: a -> Bool

-- Instance WeAccept pour Box
-- Exemple : on accepte une box si son poids <= 10
instance WeAccept Box where
    accept (Box weight _) = weight <= 10

-- Fonction qui filtre les boîtes acceptées
acceptedBoxes :: [Box] -> [Box]
acceptedBoxes boxes = filter accept boxes

-- Fonction principale : teste les fonctions
main :: IO ()
main = do
    let boxes = [Box 5 "Apple", Box 12 "Orange", Box 8 "Banana"]
    putStrLn "Boîtes acceptées :"
    print (acceptedBoxes boxes)
```

---

### **Explication**

* **`data Box = Box Int String`** : définit une boîte avec un poids et un nom.
* **`class WeAccept a where accept :: a -> Bool`** : interface pour vérifier si un objet est accepté.
* **`instance WeAccept Box where accept (Box weight _) = weight <= 10`** : on accepte une boîte si son poids est inférieur ou égal à 10.
* **`acceptedBoxes = filter accept`** : utilise `filter` avec la fonction `accept` pour ne garder que les boîtes acceptées.
* **`main`** : teste notre fonction avec une liste de boîtes et affiche les résultats.

---

### **Résultat à l’exécution**

```
Boîtes acceptées :
[Box 5 "Apple",Box 8 "Banana"]
```
