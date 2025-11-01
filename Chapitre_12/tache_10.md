### **HC12T10 – Module d’opérations mathématiques**

**Sujet :**
Créer un programme Haskell qui définit un **module d’opérations mathématiques** et démontre son utilisation dans la fonction `main`.
Le programme doit demander deux nombres à l’utilisateur et afficher les résultats des quatre opérations de base.

---

### **Correction complète**

```haskell
-- HC12T10 : Module d’opérations mathématiques (version tout-en-un)

-- Déclaration du module principal
module Main where

-- === Définition des fonctions mathématiques ===

-- Addition
addition :: Float -> Float -> Float
addition x y = x + y

-- Soustraction
soustraction :: Float -> Float -> Float
soustraction x y = x - y

-- Multiplication
multiplication :: Float -> Float -> Float
multiplication x y = x * y

-- Division avec gestion d’erreur
division :: Float -> Float -> Either String Float
division _ 0 = Left "❌ Erreur : division par zéro !"
division x y = Right (x / y)

-- === Fonction principale ===
main :: IO ()
main = do
    putStrLn "=== 🧮 Module d’opérations mathématiques ==="
    putStrLn "Entrez le premier nombre :"
    aStr <- getLine
    putStrLn "Entrez le deuxième nombre :"
    bStr <- getLine

    let a = read aStr :: Float
        b = read bStr :: Float

    putStrLn "\nRésultats :"
    putStrLn ("Addition       : " ++ show (addition a b))
    putStrLn ("Soustraction   : " ++ show (soustraction a b))
    putStrLn ("Multiplication : " ++ show (multiplication a b))

    case division a b of
        Right res -> putStrLn ("Division       : " ++ show res)
        Left err  -> putStrLn ("Division       : " ++ err)
```

---

### **Explication**

* `module Main where` : définit le **module principal** du programme.
* Chaque opération (`addition`, `soustraction`, etc.) est **une fonction pure** qui prend deux `Float`.
* `Either String Float` dans `division` permet de **gérer proprement les erreurs** :

  * `Left` contient un message d’erreur,
  * `Right` contient le résultat valide.
* La fonction `main` gère les **entrées utilisateur** et affiche chaque résultat.
* `case division a b of ...` vérifie si la division s’est bien passée avant d’afficher le résultat.

---

### **Résultat attendu à l’exécution**

#### Cas 1 : Entrée normale

```
=== 🧮 Module d’opérations mathématiques ===
Entrez le premier nombre :
12
Entrez le deuxième nombre :
4

Résultats :
Addition       : 16.0
Soustraction   : 8.0
Multiplication : 48.0
Division       : 3.0
```

#### Cas 2 : Division par zéro

```
=== 🧮 Module d’opérations mathématiques ===
Entrez le premier nombre :
7
Entrez le deuxième nombre :
0

Résultats :
Addition       : 7.0
Soustraction   : 7.0
Multiplication : 0.0
Division       : ❌ Erreur : division par zéro !
```

---

### **À retenir**

* En Haskell, on peut **gérer les erreurs sans planter le programme** grâce à `Either`.
* Un **module** peut être déclaré dans le même fichier que `main` pour simplifier un petit TP.
* Les fonctions mathématiques sont **pures** : elles ne dépendent d’aucune entrée/sortie.
* `read` convertit une chaîne (`String`) en nombre (`Float`).
* `show` fait l’inverse : transforme un nombre en texte pour l’affichage.
