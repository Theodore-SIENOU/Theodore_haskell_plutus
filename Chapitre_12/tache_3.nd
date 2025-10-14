### **HC12T3 – Fonction factorielle**

**Sujet :**
Créer un programme qui définit une fonction `factorial` pour calculer la factorielle d’un entier positif donné.

---

###  **Correction complète**

```haskell
-- Définition de la fonction factorial
factorial :: Integer -> Integer
factorial 0 = 1
factorial n = n * factorial (n - 1)

-- Fonction principale pour tester
main :: IO ()
main = do
    let number = 5
    putStrLn ("La factorielle de " ++ show number ++ " est : " ++ show (factorial number))
```

---

###  **Explication**

* La fonction `factorial` utilise **la récursion** :

  * La base : `factorial 0 = 1` (par définition, 0! = 1)
  * Le cas récursif : `n! = n * (n - 1)!`
* Le type `Integer` permet de manipuler de très grands nombres (plus grands que `Int`).
* La fonction `main` affiche le résultat pour une valeur donnée (ici `5`).

---

###  **Résultat attendu à l’exécution**

```
La factorielle de 5 est : 120
```

---
