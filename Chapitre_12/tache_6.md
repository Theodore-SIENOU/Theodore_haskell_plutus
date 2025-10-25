### **HC12T6 – Trier une liste d’entiers**

**Sujet :**
Développer un programme qui lit une liste d’entiers saisie par l’utilisateur, puis affiche cette liste triée dans l’ordre croissant.

---

### **Correction complète**

```haskell
import Data.List (sort)

-- Fonction principale
main :: IO ()
main = do
    putStrLn "Entrez une liste d'entiers séparés par des espaces :"
    input <- getLine
    let numbers = map read (words input) :: [Int]
    putStrLn "Liste triée dans l’ordre croissant :"
    print (sort numbers)
```

---

###  **Explication**

* `getLine` → lit une ligne de texte saisie par l’utilisateur.
* `words input` → découpe la chaîne en mots (par espace).
* `map read` → convertit chaque mot en entier (`Int`).
* `sort` (de `Data.List`) → trie la liste dans l’ordre croissant.
* `print` → affiche le résultat dans le terminal.

---

### **Exemple d’exécution**

```
Entrez une liste d'entiers séparés par des espaces :
9 2 5 1 7
Liste triée dans l’ordre croissant :
[1,2,5,7,9]
```

---

###  **À retenir**

* `map read (words input)` est une technique très courante pour convertir une ligne d’entrée utilisateur en liste d’entiers.
* Pour trier dans **l’ordre décroissant**, tu pourrais utiliser :

  ```haskell
  print (reverse (sort numbers))
  ```

---
