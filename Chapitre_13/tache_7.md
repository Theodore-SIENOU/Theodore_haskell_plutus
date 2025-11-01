### **HC13T7 – Utiliser un module personnalisé dans main (tout dans un seul fichier)**

**Sujet :**
Écrire un programme Haskell qui utilise une fonction `sumNonEmpty` (comme celle de `SumNonEmpty`) pour calculer la somme d’une liste de nombres.
Le programme doit **démontrer son utilisation directement dans `main`**.

---

### **Correction complète**

```haskell
-- HC13T7 : Utiliser une fonction "module" SumNonEmpty dans main
-- Tout dans un seul fichier

-- Simulation du module SumNonEmpty (fonction exportée)
sumNonEmpty :: [Int] -> Int
sumNonEmpty [] = error " Erreur : la liste est vide, impossible de calculer la somme."
sumNonEmpty xs = sum xs

-- Version safe pour ne jamais planter
sumNonEmptySafe :: [Int] -> Maybe Int
sumNonEmptySafe [] = Nothing
sumNonEmptySafe xs = Just (sum xs)

-- Fonction principale
main :: IO ()
main = do
    putStrLn " HC13T7 : Utilisation d'un module personnalisé (SumNonEmpty)"

    -- Exemple 1 : liste non vide
    let liste1 = [10, 20, 30]
    putStrLn "\n Somme de [10,20,30] avec sumNonEmpty :"
    print (sumNonEmpty liste1)

    -- Exemple 2 : liste vide
    let liste2 = []
    putStrLn "\n Test avec une liste vide (sumNonEmptySafe) :"
    case sumNonEmptySafe liste2 of
        Just s  -> print s
        Nothing -> putStrLn " Liste vide, impossible de calculer la somme."

    -- Exemple 3 : liste saisie par l'utilisateur
    putStrLn "\n Entrez des nombres séparés par des espaces :"
    input <- getLine
    let userList = map read (words input) :: [Int]
    case sumNonEmptySafe userList of
        Just s  -> putStrLn ("Somme calculée : " ++ show s)
        Nothing -> putStrLn " Liste vide, impossible de calculer la somme."
```

---

### **Explication**

* `sumNonEmpty` → fonction principale simulant le module `SumNonEmpty`.
* `sumNonEmptySafe` → version sécurisée avec `Maybe`, ne plante jamais.
* `main` :

  * teste la fonction avec une **liste fixe non vide**,
  * teste avec une **liste vide** en sécurité,
  * permet à l’**utilisateur d’entrer sa propre liste** pour calculer la somme.
* Tout est dans **un seul fichier**, exécutable directement.

---

### **Résultat attendu à l’exécution**

Supposons que l’utilisateur saisisse :

```
5 15 25
```

Sortie possible :

```
 HC13T7 : Utilisation d'un module personnalisé (SumNonEmpty)

 Somme de [10,20,30] avec sumNonEmpty :
60

 Test avec une liste vide (sumNonEmptySafe) :
 Liste vide, impossible de calculer la somme.

 Entrez des nombres séparés par des espaces :
Somme calculée : 45
```

---

### **À retenir**

* Même sans module séparé, on peut **simuler un module** en définissant une fonction dans le même fichier.
* `sumNonEmptySafe` permet de gérer les cas **liste vide** sans planter.
* L’utilisateur peut **interagir directement** via le terminal.

---
