### **HC13T5 – SumNonEmpty (version tout-en-un, safe et visibilité “restreinte”)**

**Sujet :**
Définir une fonction `sumNonEmpty` qui somme une liste non vide, en cachant les fonctions utilitaires internes (comme le message d’erreur) dans le même fichier.
Le programme doit être **exécutable directement** avec `main`.

---

### **Correction complète**

```haskell
-- HC13T5 : SumNonEmpty tout-en-un avec visibilité restreinte (fonction utilitaire privée)

-- Fonction principale : somme d'une liste non vide
sumNonEmpty :: [Int] -> Int
sumNonEmpty [] = error errorMessage  -- message géré par la fonction interne
sumNonEmpty xs = sum xs

-- Fonction utilitaire interne (private) : message d'erreur
errorMessage :: String
errorMessage = " Erreur : la liste est vide, impossible de calculer la somme."

-- Version “safe” : renvoie Maybe Int pour ne jamais planter
sumNonEmptySafe :: [Int] -> Maybe Int
sumNonEmptySafe [] = Nothing
sumNonEmptySafe xs = Just (sum xs)

-- Fonction principale
main :: IO ()
main = do
    putStrLn " Test de sumNonEmpty (avec visibilité restreinte et version safe) :"

    -- Cas 1 : liste non vide
    putStrLn "\n Somme de [5, 10, 15] (sumNonEmpty) ="
    print (sumNonEmpty [5,10,15])

    -- Cas 2 : liste vide (version classique avec error, plantera)
    putStrLn "\n Test avec une liste vide (sumNonEmpty, déclenche une erreur) :"
    -- print (sumNonEmpty [])   -- Décommenter pour tester l'erreur

    -- Cas 3 : version safe
    putStrLn "\n Test avec une liste vide (sumNonEmptySafe, ne plante pas) :"
    case sumNonEmptySafe [] of
        Just s  -> print s
        Nothing -> putStrLn " Liste vide, impossible de calculer la somme."
```

---

### **Explication**

* `errorMessage` est **interne au fichier** → simulant une **fonction privée**.
* `sumNonEmpty` utilise `errorMessage` pour signaler une liste vide (plantera si appelée).
* `sumNonEmptySafe` est la version sécurisée qui **retourne `Maybe`** et ne plante jamais.
* Tout est dans **un seul fichier**, donc compilation et exécution simples :

```bash
ghc exo5.hs -o exo5
./exo5
```

---

### **Résultat attendu**

```
 Test de sumNonEmpty (avec visibilité restreinte et version safe) :

 Somme de [5, 10, 15] (sumNonEmpty) =
30

 Test avec une liste vide (sumNonEmpty, déclenche une erreur) :
 Test avec une liste vide (sumNonEmptySafe, ne plante pas) :
 Liste vide, impossible de calculer la somme.
```

---
