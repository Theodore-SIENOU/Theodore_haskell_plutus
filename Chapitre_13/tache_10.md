### **HC13T10 – Fonction main multi-modules**

**Sujet :**
Créer une fonction `main` qui utilise des fonctions de **`System.Directory`** et **`Data.List`** pour :

1. Lister tous les fichiers du répertoire courant
2. Filtrer les fichiers contenant une sous-chaîne donnée
3. Trier les fichiers filtrés
4. Afficher les résultats triés

---

### **Correction complète**

```haskell
-- HC13T10 : Fonction main multi-modules
-- Tout dans un seul fichier

import System.Directory (getCurrentDirectory, listDirectory)
import Data.List (isInfixOf, sort)
import System.IO

-- Fonction pour filtrer les fichiers par sous-chaîne
filtrerFichiers :: String -> [FilePath] -> [FilePath]
filtrerFichiers sousChaine fichiers = filter (isInfixOf sousChaine) fichiers

-- Fonction principale
main :: IO ()
main = do
    putStrLn "🧮 HC13T10 : Main multi-modules - recherche et affichage trié des fichiers"

    -- Obtenir le répertoire courant et lister son contenu
    currentDir <- getCurrentDirectory
    fichiers <- listDirectory currentDir

    putStrLn ("\nRépertoire actuel : " ++ currentDir)

    -- Demander la sous-chaîne à l'utilisateur
    putStrLn "Entrez une sous-chaîne pour filtrer les fichiers :"
    sousChaine <- getLine

    -- Filtrer et trier les fichiers
    let fichiersFiltres = sort (filtrerFichiers sousChaine fichiers)

    -- Afficher les résultats
    putStrLn "\n Fichiers filtrés et triés :"
    if null fichiersFiltres
        then putStrLn " Aucun fichier ne correspond à la sous-chaîne."
        else mapM_ (\f -> putStrLn (" - " ++ f)) fichiersFiltres
```

---

### **Explication**

* `getCurrentDirectory` → récupère le répertoire courant
* `listDirectory` → liste tous les fichiers et dossiers
* `filtrerFichiers` → filtre les fichiers selon une **sous-chaîne** (`isInfixOf`)
* `sort` → trie la liste de fichiers filtrés
* `mapM_ putStrLn` → affiche chaque fichier sur une ligne
* Tout est dans **un seul fichier**, exécuté directement via `ghc` :

```bash
ghc hc13t10.hs -o hc13t10
./hc13t10
```

---

### **Résultat attendu à l’exécution**

Supposons que le répertoire contient :

```
notes.txt, document.pdf, image.png, test.hs
```

Entrée utilisateur : `t`

```
🧮 HC13T10 : Main multi-modules - recherche et affichage trié des fichiers

Répertoire actuel : /home/theodore/Documents
Entrez une sous-chaîne pour filtrer les fichiers :
t

 Fichiers filtrés et triés :
 - notes.txt
 - test.hs
```

---

### **À retenir**

* `System.Directory` et `Data.List` peuvent être combinés pour effectuer **des opérations complexes** sur les fichiers.
* `filter + sort` → technique classique pour **filtrer et trier des listes** en Haskell
* Ce programme montre **l’intégration de plusieurs modules dans `main`** et l’affichage des résultats de manière claire.

---
