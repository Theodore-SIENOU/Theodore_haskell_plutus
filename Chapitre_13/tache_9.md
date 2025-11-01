### **HC13T9 – Renommer un espace de noms de module**

**Sujet :**
Créer une fonction qui démontre le **renommage d’un module importé** et utilise des fonctions des deux modules renommés.
On simule deux modules (`ModuleA` et `ModuleB`) avec des fonctions portant le même nom, et on montre comment les distinguer.

---

### **Correction complète**

```haskell
-- HC13T9 : Renommer un espace de noms de module
-- Version tout-en-un (exécutable)

-- === Simulation de ModuleA ===
afficheMessage_ModuleA :: String -> String
afficheMessage_ModuleA nom = " ModuleA dit bonjour à " ++ nom

-- === Simulation de ModuleB ===
afficheMessage_ModuleB :: String -> String
afficheMessage_ModuleB nom = " ModuleB vous salue, " ++ nom

-- === Fonction principale ===
main :: IO ()
main = do
    putStrLn "🧮 HC13T9 : Renommer un espace de noms de module"

    -- Utilisation des fonctions en simulant le renommage
    putStrLn "\n Appel de la fonction du module renommé ModA :"
    putStrLn (afficheMessage_ModuleA "Theo")

    putStrLn "\n Appel de la fonction du module renommé ModB :"
    putStrLn (afficheMessage_ModuleB "Theo")

    putStrLn "\n Démonstration : Les modules ont été renommés via un préfixe explicite."
```

---

### **Explication**

* Dans Haskell, on peut **renommer un module importé** avec `as` :

```haskell
import qualified ModuleA as ModA
import qualified ModuleB as ModB
```

* Ensuite, on appelle les fonctions via le **nouveau nom du module** :

```haskell
ModA.afficheMessage "Theo"
ModB.afficheMessage "Theo"
```

* Ici, dans **un seul fichier**, on **simule ce comportement** en donnant un **préfixe explicite aux fonctions** :
  `afficheMessage_ModuleA` et `afficheMessage_ModuleB`.
* Cela montre **le même principe** : éviter les conflits et distinguer les fonctions provenant de modules différents.

---

### **Résultat attendu à l’exécution**

```
🧮 HC13T9 : Renommer un espace de noms de module

 Appel de la fonction du module renommé ModA :
 ModuleA dit bonjour à Theo

 Appel de la fonction du module renommé ModB :
 ModuleB vous salue, Theo

 Démonstration : Les modules ont été renommés via un préfixe explicite.
```

---

### **À retenir**

* `import qualified ModuleX as Alias` → renomme un module pour simplifier l’utilisation.
* Permet de **résoudre les conflits de noms**.
* Même dans un fichier unique, on peut **simuler ce comportement** avec des préfixes explicites.
* C’est une bonne pratique pour **rendre le code clair et éviter les collisions**.

---
