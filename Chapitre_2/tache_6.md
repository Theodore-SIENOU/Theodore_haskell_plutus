HC2T6 - Tâche 6 : Comprendre Int vs Luge

###  Objectif

* Définir deux variables numériques :

  1. `variableNombre` de type `Int` avec la valeur $2^{62}$.
  2. `bigNumber` de type `Integer` avec la valeur $2^{127}$.
* Tester en GHCi l’évaluation de `2^64 :: Int`.

---

###  Correction

```haskell
-- Fichier : Main.hs

-- Définition de variables numériques
variableNombre :: Int
variableNombre = 2 ^ 62

bigNumber :: Integer
bigNumber = 2 ^ 127

main :: IO ()
main = do
    putStrLn " Variables numériques en Haskell"

    print ("variableNombre (2^62, Int) = " ++ show variableNombre)
    print ("bigNumber (2^127, Integer) = " ++ show bigNumber)

    putStrLn "\n Attention : test de débordement avec Int"
    print (2 ^ 64 :: Int)   -- Ici, débordement attendu
```

---

###  Explications

1. **Int**

   * Type entier **borné** (taille dépend de la machine, souvent 64 bits).
   * Peut déborder si on dépasse sa capacité max.

   Exemple :

   ```haskell
   maxBound :: Int
   -- Sur 64 bits → 9223372036854775807
   ```

2. **Integer**

   * Type entier **illimité** en Haskell (arbitrairement grand).
   * Pas de débordement.

3. **Débordement avec Int**

   * `2 ^ 64 :: Int` est **trop grand pour tenir dans un Int** → il va “boucler” (overflow).
   * Résultat dépend de l’implémentation, mais sur GHCi 64 bits on obtient :

     ```haskell
     2^64 :: Int
     0
     ```

---

###  Exemple d’exécution attendue

```
 Variables numériques en Haskell
"variableNombre (2^62, Int) = 4611686018427387904"
"bigNumber (2^127, Integer) = 170141183460469231731687303715884105728"

⚠️ Attention : test de débordement avec Int
0
