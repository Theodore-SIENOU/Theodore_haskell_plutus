### **HC13T8 – Importations qualifiées pour les conflits de noms**

**Sujet :**
Montrer comment gérer les conflits de noms entre deux modules importés en utilisant les **importations qualifiées** (`qualified import`).
Dans ce programme, on simule deux modules (`ModuleA` et `ModuleB`) qui ont chacun une fonction portant le même nom (`afficheMessage`).
On résout le conflit en utilisant des **préfixes explicites**.

---

### **Correction complète**

```haskell
-- HC13T8 : Importations qualifiées pour éviter les conflits de noms
--  Version tout-en-un (exécutable directement)

-- Simulation du module A
afficheMessageA :: String -> String
afficheMessageA nom = " ModuleA dit bonjour à " ++ nom

-- Simulation du module B
afficheMessageB :: String -> String
afficheMessageB nom = " ModuleB vous salue, " ++ nom

-- Fonction principale
main :: IO ()
main = do
    putStrLn " HC13T8 : Gestion des conflits de noms avec importations qualifiées"

    putStrLn "\n Appel de la fonction de ModuleA :"
    putStrLn (afficheMessageA "Theo")

    putStrLn "\n Appel de la fonction de ModuleB :"
    putStrLn (afficheMessageB "Theo")

    putStrLn "\n Démonstration : Les deux fonctions ont le même rôle mais viennent de modules différents."
```

---

### **Explication**

* Si deux modules exportent une fonction ayant le même nom (`afficheMessage`), il y a **conflit de noms**.
* Pour éviter ce conflit, on utilise une **importation qualifiée** :

  ```haskell
  import qualified ModuleA
  import qualified ModuleB
  ```

  puis on appelle :

  ```haskell
  ModuleA.afficheMessage "Theo"
  ModuleB.afficheMessage "Theo"
  ```
* Dans cette version “tout-en-un”, on simule ces modules avec deux fonctions nommées différemment :
  `afficheMessageA` et `afficheMessageB`, pour **illustrer le même concept**.

---

### **Résultat attendu à l’exécution**

```
 HC13T8 : Gestion des conflits de noms avec importations qualifiées

 Appel de la fonction de ModuleA :
 ModuleA dit bonjour à Theo

 Appel de la fonction de ModuleB :
 ModuleB vous salue, Theo

 Démonstration : Les deux fonctions ont le même rôle mais viennent de modules différents.
```

---

### **À retenir**

* En cas de **conflit de noms entre deux modules**, utilisez :

  ```haskell
  import qualified NomDuModule
  ```
* Cela vous oblige à **préciser le nom du module** avant chaque appel :
  `ModuleA.fonction`, `ModuleB.fonction`.
* C’est une **bonne pratique** pour éviter les collisions et rendre le code plus clair.
* Ici, tout le code est dans **un seul fichier** pour la simplicité d’exécution.

---
