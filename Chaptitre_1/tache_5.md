HC1T5 - Tâche 5 : Paresse en Haskell

 Objectif

Créer une fonction infiniteNumbers qui :

    génère une liste infinie de nombres entiers croissants à partir de 1

    est paresseuse : ne calcule les éléments que lorsqu’ils sont demandés

    permet d’extraire seulement les n premiers éléments

 Correction complète avec main

      -- Fichier : Main.hs
      
      -- Génère une liste infinie de nombres à partir de 1
      infiniteNumbers :: [Int]
      infiniteNumbers = [1..]
      
      -- Fonction principale pour tester
      main :: IO ()
      main = do
          let n = 10
          let premiers = take n infiniteNumbers
          putStrLn ("Les " ++ show n ++ " premiers nombres de infiniteNumbers :")
          print premiers

 Explication ligne par ligne

infiniteNumbers :: [Int]
infiniteNumbers = [1..]

    Crée une liste infinie de Int démarrant à 1.

    Grâce à la paresse, Haskell ne calcule les valeurs que lorsqu'on en a besoin.

let premiers = take n infiniteNumbers

    take n extrait les n premiers éléments de la liste infinie.

    Haskell s’arrête automatiquement après avoir obtenu ces n valeurs (grâce à l’évaluation paresseuse).

putStrLn (...)` et `print premiers

    Affiche les n premiers éléments extraits de la liste.

 Résultat attendu à l’exécution

      Les 10 premiers nombres de infiniteNumbers :
      [1,2,3,4,5,6,7,8,9,10]
