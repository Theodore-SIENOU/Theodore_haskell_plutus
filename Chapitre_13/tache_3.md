### **HC13T3 – Trier et retourner les fichiers filtrés**

**Sujet :**
Implémenter une fonction qui **filtre** et **trie** les noms de fichiers du **répertoire courant**,
en utilisant les fonctions **`filter`** et **`sort`** du module **`Data.List`**.
Le programme doit demander une sous-chaîne à rechercher, filtrer les fichiers correspondants,
puis les **afficher triés par ordre alphabétique**.

---

### **Correction complète**

```haskell
-- HC13T3 : Trier et retourner les fichiers filtrés

import System.Directory (getCurrentDirectory, listDirectory)
import Data.List (isInfixOf, sort)
import System.IO

-- Fonction pour filtrer et trier les fichiers selon une sous-chaîne
filtrerEtTrierFichiers :: String -> [FilePath] -> [FilePath]
filtrerEtTrierFichiers sousChaine fichiers =
    sort (filter (isInfixOf sousChaine) fichiers)

-- Fonction principale
main :: IO ()
main = do
    putStrLn "===  Trier et retourner les fichiers filtrés ==="

    -- Obtenir le répertoire courant
    currentDir <- getCurrentDirectory
    contents <- listDirectory currentDir

    putStrLn ("\nRépertoire actuel : " ++ currentDir)
    putStrLn "Entrez une sous-chaîne à rechercher dans les noms de fichiers :"
    sousChaine <- getLine

    let resultats = filtrerEtTrierFichiers sousChaine contents

    putStrLn "\nRésultats filtrés et triés :"
    if null resultats
        then putStrLn " Aucun fichier ne correspond à cette sous-chaîne."
        else mapM_ (\f -> putStrLn (" - " ++ f)) resultats
```

---

### **Explication**

* `listDirectory` → récupère la liste de tous les fichiers et dossiers du répertoire courant.
* `isInfixOf` → vérifie si la sous-chaîne donnée apparaît dans le nom du fichier.
* `filter` → garde seulement les fichiers dont le nom contient la sous-chaîne.
* `sort` → trie la liste obtenue **par ordre alphabétique croissant**.
* La fonction `filtrerEtTrierFichiers` combine ces deux opérations dans une seule ligne.
* La fonction `main` gère l’interaction utilisateur et affiche les résultats.

---

### **Résultat attendu à l’exécution**

#### Cas 1 : Plusieurs fichiers trouvés

```
===  Trier et retourner les fichiers filtrés ===

Répertoire actuel : /home/theodore/Documents
Entrez une sous-chaîne à rechercher dans les noms de fichiers :
doc

Résultats filtrés et triés :
 - doc_exemple.txt
 - document1.pdf
 - document2.pdf
```

#### Cas 2 : Aucun fichier trouvé

```
===  Trier et retourner les fichiers filtrés ===

Répertoire actuel : /home/theodore/Documents
Entrez une sous-chaîne à rechercher dans les noms de fichiers :
photo

Résultats filtrés et triés :
 Aucun fichier ne correspond à cette sous-chaîne.
```

---

### **À retenir**

* `filter` sélectionne les éléments d’une liste selon une **condition logique**.
* `sort` trie une liste **en ordre croissant** (alphabétique pour les chaînes).
* En combinant `filter` et `sort`, on obtient une recherche **simple et élégante**.
* Pour rendre le programme plus robuste, on pourrait aussi :

  * Ignorer la **casse** (`map toLower`) ;
  * Afficher d’abord les **fichiers** avant les **dossiers** ;
  * Ajouter un **tri inverse** (`reverse (sort ...)`).

---
