 **HC4T1 – Tâche 1 : une penderie de service après une perturbation en dangerÉmentaire**


###  Objectif

* Créer une fonction `meteoRapport :: String -> String`
* Prend en entrée une condition météo (`"ensoleillé"`, `"pluvieux"`, `"trouble"`, etc.)
* Retourne un message adapté avec **pattern matching** :

  * `"ensoleillé"` → `"Il fait beau et ensoleillé"`
  * `"pluvieux"` → `"N'oublie pas ton parapluie"`
  * `"trouble"` → `"Un peu gris, mais pas de pluie pour l'instant"`
  * Sinon → `"Météo inconnue"`



###  Correction complète avec `main`

```haskell
-- Fichier : Main.hs

-- Fonction qui donne un rapport météo
meteoRapport :: String -> String
meteoRapport condition = case condition of
    "ensoleillé" -> "Il fait beau et ensoleillé"
    "pluvieux"   -> "N'oublie pas ton parapluie"
    "trouble"    -> "Un peu gris, mais pas de pluie pour l'instant"
    _            -> "Météo inconnue"

-- Fonction principale pour tester
main :: IO ()
main = do
    putStrLn $ "meteoRapport \"ensoleillé\" = " ++ meteoRapport "ensoleillé"
    putStrLn $ "meteoRapport \"pluvieux\" = " ++ meteoRapport "pluvieux"
    putStrLn $ "meteoRapport \"trouble\" = " ++ meteoRapport "trouble"
    putStrLn $ "meteoRapport \"orage\" = " ++ meteoRapport "orage"
```



###  Explication

```haskell
meteoRapport condition = case condition of
```

* On fait un **pattern matching** sur la chaîne entrée.

```haskell
"ensoleillé" -> "Il fait beau et ensoleillé"
```

* Si la chaîne est exactement `"ensoleillé"`, on renvoie le message correspondant.

```haskell
_ -> "Météo inconnue"
```

* `_` capture **tout ce qui ne correspond pas** aux autres cas.



###  Résultat attendu

```
meteoRapport "ensoleillé" = Il fait beau et ensoleillé
meteoRapport "pluvieux" = N'oublie pas ton parapluie
meteoRapport "trouble" = Un peu gris, mais pas de pluie pour l'instant
meteoRapport "orage" = Météo inconnue
```
