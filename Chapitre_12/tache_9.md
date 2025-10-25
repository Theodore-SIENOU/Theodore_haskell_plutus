### **HC12T9 – Lire et afficher le contenu d’un fichier**

**Sujet :**
Écrire un programme Haskell qui lit un fichier texte et affiche son contenu dans le terminal.
Le programme doit **gérer les erreurs** si le fichier n’existe pas.

---

###  **Correction complète**

```haskell
import System.IO
import Control.Exception (catch, IOException)

-- Fonction pour lire et afficher le contenu d’un fichier
readFileSafe :: FilePath -> IO ()
readFileSafe filename = do
    contentOrError <- catch (readFile filename >>= \content -> return (Right content))
                            (\e -> return (Left (show (e :: IOException))))
    case contentOrError of
        Right content -> do
            putStrLn "\n📘 Contenu du fichier :"
            putStrLn content
        Left errorMsg -> do
            putStrLn "\n❌ Erreur : impossible de lire le fichier."
            putStrLn ("Détails : " ++ errorMsg)

-- Fonction principale
main :: IO ()
main = do
    putStrLn "Entrez le nom du fichier à lire :"
    filename <- getLine
    readFileSafe filename
```

---

###  **Explication**

* `readFile` : lit le contenu complet d’un fichier texte.
* `catch` : capture une exception (par exemple, fichier introuvable).
* `IOException` : type d’erreur pour les entrées/sorties.
* Si la lecture réussit → affiche le contenu.
* Si une erreur se produit → affiche un message d’erreur clair.

---

###  **Résultat attendu à l’exécution**

####  Cas 1 : le fichier existe

```
Entrez le nom du fichier à lire :
notes.txt

 Contenu du fichier :
Haskell est un langage purement fonctionnel.
Ceci est un test de lecture de fichier.
```

####  Cas 2 : le fichier n’existe pas

```
Entrez le nom du fichier à lire :
absent.txt

 Erreur : impossible de lire le fichier.
Détails : absent.txt: openFile: does not exist (No such file or directory)
```

---

###  **À retenir**

* `readFile` retourne un `IO String`.
* Les erreurs d’E/S doivent toujours être **gérées** avec `catch`.
* Ce programme fonctionne pour tout fichier texte (UTF-8).

---
