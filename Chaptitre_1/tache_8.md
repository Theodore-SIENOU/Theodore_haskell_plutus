HC1T8 - Tâche 8 : Fonctions d’ordre supérieur

 Objectif

Créer une fonction applyTwice qui :

    prend une fonction f et une valeur x en entrée

    applique f deux fois de suite sur x (c’est-à-dire f (f x))

    doit être pure et générique, pouvant fonctionner sur tout type compatible avec f

 Correction complète avec main

      -- Fichier : Main.hs
      
      -- Applique une fonction deux fois sur une valeur
      applyTwice :: (a -> a) -> a -> a
      applyTwice f x = f (f x)
      
      -- Fonction principale pour tester
      main :: IO ()
      main = do
          let f = (+3)           -- fonction qui ajoute 3
          let x = 10
          let g = reverse        -- fonction qui inverse une liste
          let xs = "abcd"
      
          putStrLn $ "applyTwice (+3) 10 = " ++ show (applyTwice f x)
          putStrLn $ "applyTwice reverse \"abcd\" = " ++ applyTwice g xs

 Explication ligne par ligne

      applyTwice :: (a -> a) -> a -> a

applyTwice prend une fonction f de type a -> a et une valeur x de type a.

Retourne une valeur de type a.

      applyTwice f x = f (f x)

Applique la fonction f une première fois sur x, puis une deuxième fois sur le résultat.

      let f = (+3)`

Exemple avec une fonction qui ajoute 3.

      let g = reverse`

Exemple avec la fonction reverse qui inverse une liste ou une chaîne de caractères.

    putStrLn ...`

Affiche les résultats avec show ou directement (pour les chaînes).

 Résultat attendu à l’exécution

      applyTwice (+3) 10 = 16
      applyTwice reverse "abcd" = abcd
