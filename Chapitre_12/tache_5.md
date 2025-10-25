### **HC12T5 – Vérification de palindrome**

**Sujet :**
Créer un programme qui définit une fonction `isPalindrome` pour vérifier si une chaîne est un **palindrome**.
Utiliser la fonction `main` pour tester cela avec une **entrée utilisateur**.

---

###  **Correction complète**

```haskell
import Data.Char (toLower, isAlphaNum)

-- Fonction pour vérifier si une chaîne est un palindrome
isPalindrome :: String -> Bool
isPalindrome str =
    let cleaned = map toLower (filter isAlphaNum str)
    in cleaned == reverse cleaned

-- Fonction principale
main :: IO ()
main = do
    putStrLn "Entrez une phrase :"
    input <- getLine
    if isPalindrome input
        then putStrLn "C'est un palindrome ! "
        else putStrLn "Ce n'est pas un palindrome. "
```

---

###  **Explication**

* `filter isAlphaNum str` → retire les espaces, ponctuations, etc.
* `map toLower` → met tout en minuscules pour ignorer les différences de casse.
* On compare ensuite la chaîne nettoyée à sa version inversée avec `reverse`.
* Si elles sont identiques → la phrase est un palindrome.

---

###  **Résultat attendu à l’exécution**

#### Exemple 1 :

```
Entrez une phrase :
Kayak
C'est un palindrome ! 
```

#### Exemple 2 :

```
Entrez une phrase :
Bonjour
Ce n'est pas un palindrome. 
```

#### Exemple 3 :

```
Entrez une phrase :
Élu par cette crapule
C'est un palindrome ! 
```

---
