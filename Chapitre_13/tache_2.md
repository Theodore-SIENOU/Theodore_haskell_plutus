### **Correction complète**

```haskell
-- HC13T2 : Filtrer les fichiers par sous-chaîne

import System.Directory (getCurrentDirectory, listDirectory)
import Data.List (isInfixOf)
import System.IO

-- Fonction pour filtrer les fichiers selon une sous-chaîne
filtrerFichiers :: String -> [FilePath] -> [FilePath]
filtrerFichiers sousChaine fichiers =
    filter (isInfixOf sousChaine) fichiers

-- Fonction principale
main :: IO ()
main = do
    putStrLn "===  Filtrer les fichiers par sous-chaîne ==="

    -- Obtenir le répertoire courant
    currentDir <- getCurrentDirectory
    contents <- listDirectory currentDir

    putStrLn ("\nRépertoire actuel : " ++ currentDir)
    putStrLn "Entrez une sous-chaîne à rechercher dans les noms de fichiers :"
    sousChaine <- getLine

    let resultats = filtrerFichiers sousChaine contents

    putStrLn "\nRésultats du filtrage :"
    if null resultats
        then putStrLn " Aucun fichier ne correspond à cette sous-chaîne."
        else mapM_ (\f -> putStrLn (" - " ++ f)) resultats
```

---

### **Explication**

* `listDirectory` → récupère tous les fichiers et dossiers du répertoire courant.
* `isInfixOf` (du module `Data.List`) → vérifie si une **sous-chaîne** est **contenue** dans une autre chaîne.

  * Exemple : `isInfixOf "test" "notes.txt"` → `True`.
* `filter` → garde seulement les éléments qui vérifient une condition.
* `filtrerFichiers` applique `filter` avec `isInfixOf` à la liste de fichiers.
* `mapM_ putStrLn` → affiche la liste des résultats.
* Gestion du cas vide (`if null resultats`) pour un message clair.

---

### **Résultat attendu à l’exécution**

#### Cas 1 : Fichiers trouvés

```
===  Filtrer les fichiers par sous-chaîne ===

Répertoire actuel : /home/theodore/Documents
Entrez une sous-chaîne à rechercher dans les noms de fichiers :
note

Résultats du filtrage :
 - notes.txt
 - carnet_notes.csv
```

#### Cas 2 : Aucun fichier trouvé

```
===  Filtrer les fichiers par sous-chaîne ===

Répertoire actuel : /home/theodore/Documents
Entrez une sous-chaîne à rechercher dans les noms de fichiers :
photo

Résultats du filtrage :
 Aucun fichier ne correspond à cette sous-chaîne.
```

---

### **À retenir**

* `Data.List.isInfixOf` est idéale pour chercher une **partie de mot** dans une chaîne.
* `filter` permet de **sélectionner** les éléments d’une liste selon une condition.
* On peut combiner les deux pour des filtres simples et puissants.
* Pour un vrai outil de recherche, on pourrait aussi :

  * Ignorer la **casse** (`toLower`) ;
  * Filtrer uniquement les **fichiers** (en excluant les dossiers) avec `doesFileExist`.

---
