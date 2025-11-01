### **HC13T6 – Convertir des fichiers filtrés en Map**

**Sujet :**
Créer une fonction qui transforme une **liste de fichiers filtrés** en **`Data.Map`**, avec :

* clé = nom du fichier
* valeur = longueur du nom du fichier

Le programme doit afficher la liste filtrée et la Map dans le terminal.

---

### **Correction complète (tout dans un seul fichier)**

```haskell
-- HC13T6 : Convertir une liste de fichiers filtrés en Map
-- Tout dans un seul fichier

import Data.Map (Map)
import qualified Data.Map as Map
import Data.List (isInfixOf)
import System.Directory (listDirectory, getCurrentDirectory)
import System.IO

-- Fonction pour filtrer les fichiers selon une sous-chaîne
filtrerFichiers :: String -> [FilePath] -> [FilePath]
filtrerFichiers sousChaine fichiers = filter (isInfixOf sousChaine) fichiers

-- Fonction pour convertir une liste de fichiers en Map (clé = nom, valeur = longueur)
fichiersToMap :: [FilePath] -> Map FilePath Int
fichiersToMap fichiers = Map.fromList [(f, length f) | f <- fichiers]

-- Fonction principale
main :: IO ()
main = do
    putStrLn " HC13T6 : Convertir fichiers filtrés en Map"

    -- Obtenir le répertoire courant et lister son contenu
    currentDir <- getCurrentDirectory
    contents <- listDirectory currentDir

    putStrLn ("\nRépertoire actuel : " ++ currentDir)

    -- Demander la sous-chaîne à l'utilisateur
    putStrLn "Entrez une sous-chaîne pour filtrer les fichiers :"
    sousChaine <- getLine

    -- Filtrer les fichiers
    let fichiersFiltres = filtrerFichiers sousChaine contents
    putStrLn "\nFichiers filtrés :"
    if null fichiersFiltres
        then putStrLn " Aucun fichier ne correspond à la sous-chaîne."
        else mapM_ (\f -> putStrLn (" - " ++ f)) fichiersFiltres

    -- Convertir la liste filtrée en Map
    let fichiersMap = fichiersToMap fichiersFiltres
    putStrLn "\n Map des fichiers filtrés (nom -> longueur) :"
    print fichiersMap
```

---

### **Explication**

* `filtrerFichiers` → sélectionne les fichiers contenant la **sous-chaîne**.
* `fichiersToMap` → crée une `Map` où chaque **clé** = nom du fichier, **valeur** = longueur du nom :

```haskell
[(f, length f) | f <- fichiers]
```

* `Map.fromList` transforme cette liste de tuples en **Map Haskell**.
* `main` affiche à la fois la **liste filtrée** et la **Map correspondante**.
* Tout est dans **un seul fichier**, facile à compiler et exécuter :

```bash
ghc hc13t6.hs -o hc13t6
./hc13t6
```

---

### **Résultat attendu à l’exécution**

Supposons que le répertoire contient :

```
notes.txt, document.pdf, image.png, test.hs
```

Entrée utilisateur : `t`

```
 HC13T6 : Convertir fichiers filtrés en Map

Répertoire actuel : /home/theodore/Documents
Entrez une sous-chaîne pour filtrer les fichiers :
t

Fichiers filtrés :
 - notes.txt
 - test.hs

 Map des fichiers filtrés (nom -> longueur) :
fromList [("notes.txt",9),("test.hs",7)]
```

---

### **À retenir**

* `Data.Map` permet de créer des **structures clé/valeur** à partir de listes.
* Combiné à `filter`, on peut **filtrer et organiser rapidement** les fichiers.
* Tout est exécuté dans **un seul fichier**, ce qui correspond exactement à ton modèle.

---
