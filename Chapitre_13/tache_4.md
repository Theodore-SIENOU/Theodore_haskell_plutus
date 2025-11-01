### **HC13T4 – SumNonEmpty (version safe)**

**Sujet :**
Écrire un programme Haskell qui définit une fonction `sumNonEmptySafe` retournant la somme d’une liste non vide.
Si la liste est vide, le programme doit **gérer l’erreur proprement** sans planter.

---

### **Correction complète**

```haskell
-- HC13T4 : Module SumNonEmpty (version safe)

-- Fonction sumNonEmptySafe : retourne Maybe Int
sumNonEmptySafe :: [Int] -> Maybe Int
sumNonEmptySafe [] = Nothing
sumNonEmptySafe xs = Just (sum xs)

-- Fonction principale
main :: IO ()
main = do
    putStrLn " Test de la fonction sumNonEmptySafe :"

    -- Cas 1 : liste non vide
    putStrLn "\n Somme de [1, 2, 3, 4] ="
    case sumNonEmptySafe [1, 2, 3, 4] of
        Just s  -> print s
        Nothing -> putStrLn " Liste vide, impossible de calculer la somme."

    -- Cas 2 : liste vide
    putStrLn "\n Test avec une liste vide :"
    case sumNonEmptySafe [] of
        Just s  -> print s
        Nothing -> putStrLn " Liste vide, impossible de calculer la somme."
```

---

### **Explication**

* `sumNonEmptySafe` utilise le type `Maybe` :

  * `Nothing` → la liste est vide
  * `Just somme` → somme calculée si la liste n’est pas vide

* `case ... of` permet de **tester la valeur retournée** et d’afficher un message approprié.

* Avec cette version, le programme **ne plante jamais**, même si la liste est vide.

---

### **Résultat attendu à l’exécution**

```
 Test de la fonction sumNonEmptySafe :

 Somme de [1, 2, 3, 4] =
10

 Test avec une liste vide :
 Liste vide, impossible de calculer la somme.
```

---

### **À retenir**

* `Maybe` est idéal pour gérer des **résultats optionnels** de façon sûre.
* `Just x` = valeur calculée, `Nothing` = absence de valeur.
* `case ... of` permet de gérer proprement les deux cas.
* Cette méthode est **préférable à `error`**, car le programme **continue à s’exécuter**.

---
