**HC8T7 - Tâche 7 : Types de données et description d’animaux**

**Sujet**

* Définir un type `Animal` avec les constructeurs :

  * `Dog String` pour un chien avec son nom
  * `Cat String` pour un chat avec son nom
* Créer une fonction `describeAnimal :: Animal -> String` qui décrit l’animal.
* Créer des instances pour un chien et un chat.

---

**Correction complète**

```haskell
-- Main.hs

-- Définition du type Animal
data Animal
    = Dog String
    | Cat String
    deriving (Show, Eq)

-- Fonction pour décrire un animal
describeAnimal :: Animal -> String
describeAnimal (Dog name) = "Ceci est un chien nommé " ++ name ++ "."
describeAnimal (Cat name) = "Ceci est un chat nommé " ++ name ++ "."

-- Création d'instances d'animaux
myDog :: Animal
myDog = Dog "Rex"

myCat :: Animal
myCat = Cat "Mimi"

-- Fonction principale pour tester
main :: IO ()
main = do
    putStrLn $ describeAnimal myDog
    putStrLn $ describeAnimal myCat
```

---

**Explication**

* `data Animal = Dog String | Cat String` : type avec deux variantes, chaque constructeur prend un nom.
* `describeAnimal` utilise le **pattern matching** pour retourner une description selon le type d’animal.
* `myDog` et `myCat` sont des exemples concrets d’instances.
* `deriving (Show, Eq)` permet l’affichage et la comparaison des animaux si besoin.

---

**Exemple de résultat à l’exécution**

```
Ceci est un chien nommé Rex.
Ceci est un chat nommé Mimi.
```
