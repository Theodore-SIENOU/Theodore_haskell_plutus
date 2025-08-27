**HC4T2 – Tâche 2 :  carte d'identité électricé de télévision**

 Objectif
Créer une fonction `dayType :: String -> String`

* Prend en entrée un jour de la semaine.
* Retourne :

  * `"Samedi"` ou `"Dimanche"` → `"C'est le week-end"`
  * Tout autre jour valide (Lundi → Vendredi) → `"C'est un jour de semaine"`
  * Sinon → `"Jour invalide"`

 Correction complète avec `main`

```haskell
-- Définition de la fonction
dayType :: String -> String
dayType jour =
  case jour of
    "Samedi"   -> "C'est le week-end"
    "Dimanche" -> "C'est le week-end"
    "Lundi"    -> "C'est un jour de semaine"
    "Mardi"    -> "C'est un jour de semaine"
    "Mercredi" -> "C'est un jour de semaine"
    "Jeudi"    -> "C'est un jour de semaine"
    "Vendredi" -> "C'est un jour de semaine"
    _          -> "Jour invalide"

-- Programme principal pour tester
main :: IO ()
main = do
  putStrLn (dayType "Lundi")
  putStrLn (dayType "Samedi")
  putStrLn (dayType "Dimanche")
  putStrLn (dayType "Funday")
```
