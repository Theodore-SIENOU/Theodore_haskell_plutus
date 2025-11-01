### **HC13T1 – Lister les fichiers du répertoire courant**

**Sujet :**
Créer un programme Haskell qui **liste tous les fichiers** du répertoire courant en utilisant le module **`System.Directory`**.
Le programme doit afficher proprement le nom de chaque fichier et dossier trouvé.

---

### **Correction complète**

```haskell
-- HC13T1 : Lister les fichiers du répertoire courant

import System.Directory (getCurrentDirectory, listDirectory)
import System.IO

-- Fonction principale
main :: IO ()
main = do
    putStrLn "===  Liste des fichiers du répertoire courant ==="

    -- Obtenir le chemin du répertoire courant
    currentDir <- getCurrentDirectory

    putStrLn ("\nRépertoire actuel : " ++ currentDir)

    -- Lister le contenu du répertoire
    contents <- listDirectory currentDir

    putStrLn "\nContenu du répertoire :"
    if null contents
        then putStrLn "📭 Aucun fichier ni dossier trouvé."
        else mapM_ (\name -> putStrLn (" - " ++ name)) contents
```

---

### **Explication**

* `import System.Directory` : permet d’accéder aux fonctions liées au système de fichiers.
* `getCurrentDirectory` : renvoie le **chemin absolu** du dossier où le programme est exécuté.
* `listDirectory` : renvoie la **liste des fichiers et dossiers** du répertoire donné.
* `mapM_` : applique une action (`putStrLn`) à chaque élément de la liste.
* `if null contents` : vérifie si la liste est vide avant d’afficher le résultat.

---

### **Résultat attendu à l’exécution**

#### Cas 1 : répertoire contenant des fichiers

```
===  Liste des fichiers du répertoire courant ===

Répertoire actuel : /home/theodore/Documents

Contenu du répertoire :
 - main.hs
 - notes.txt
 - image.png
 - dossierTP
```

#### Cas 2 : répertoire vide

```
===  Liste des fichiers du répertoire courant ===

Répertoire actuel : /home/theodore/test

Contenu du répertoire :
 Aucun fichier ni dossier trouvé.
```

---

### **À retenir**

* `System.Directory` est le module standard pour **gérer le système de fichiers** en Haskell.
* `listDirectory` ne montre **pas les fichiers cachés** (ceux qui commencent par `.`).
* On peut facilement combiner `listDirectory` avec d’autres fonctions comme :

  * `doesFileExist` → pour vérifier si c’est un fichier ;
  * `doesDirectoryExist` → pour savoir si c’est un dossier.
* `mapM_` est la bonne manière d’itérer sur une liste d’actions en Haskell (comme `putStrLn`).

---
