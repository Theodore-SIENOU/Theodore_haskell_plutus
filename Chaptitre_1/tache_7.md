HC1T7 - Tâche 7 : Conversion Fahrenheit/Celsius

 Objectif

Écrire une fonction fToC qui :

    prend une température en degrés Fahrenheit

    retourne la température correspondante en degrés Celsius

    utilise une signature de type générique (Fractional a => a -> a)

    doit être pure (pas d’entrée/sortie)

 Correction complète avec main

      -- Fichier : Main.hs
      
      -- Convertit des degrés Fahrenheit en Celsius
      fToC :: Fractional a => a -> a
      fToC f = (f - 32) * 5 / 9
      
      -- Fonction principale pour tester
      main :: IO ()
      main = do
          let t1 = 32
          let t2 = 212
          let t3 = 98.6
      
          putStrLn $ "fToC " ++ show t1 ++ "°F = " ++ show (fToC t1) ++ "°C"
          putStrLn $ "fToC " ++ show t2 ++ "°F = " ++ show (fToC t2) ++ "°C"
          putStrLn $ "fToC " ++ show t3 ++ "°F = " ++ show (fToC t3) ++ "°C"

 Explication ligne par ligne

          fToC :: Fractional a => a -> a

 La fonction accepte tout type fractionnaire (Float, Double, etc.).

 Fractional est requis car on divise par 9.

          fToC f = (f - 32) * 5 / 9

Formule standard : C=(F−32)×59C=9(F−32)×5​

       let t1 = 32
       let t2 = 212
       let t3 = 98.6

On choisit 3 températures typiques à tester.

       print ("fToC " ++ show t1 ++ "°F = " ++ show (fToC t1) ++ "°C")

Affiche la conversion avec unités pour plus de clarté.

 Résultat attendu à l’exécution

      "fToC 32.0°F = 0.0°C"
      "fToC 212.0°F = 100.0°C"
      "fToC 98.6°F = 37.0°C"

