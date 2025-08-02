HC1T6 - Tâche 6 : Utilisation de signatures de type

 Objectif

Définir une fonction addNumbers qui :

    prend deux valeurs numériques en paramètres

    retourne leur somme

    utilise une signature de type générique avec la contrainte Num

    doit être pure (mêmes entrées → même sortie)

 Correction complète avec main

      -- Fichier : Main.hs
      
      -- Additionne deux nombres de n'importe quel type numérique
      addNumbers :: Num a => a -> a -> a
      addNumbers x y = x + y
      
      -- Fonction principale pour tester
      main :: IO ()
      main = do
          let a = 5 :: Int
          let b = 7 :: Int
          let c = 3.5 :: Float
          let d = 2.0 :: Float
          let e = 100000000000 :: Integer
          let f = 1 :: Integer
      
          print ("addNumbers " ++ show a ++ " " ++ show b ++ " = " ++ show (addNumbers a b))
          print ("addNumbers " ++ show c ++ " " ++ show d ++ " = " ++ show (addNumbers c d))
          print ("addNumbers " ++ show e ++ " " ++ show f ++ " = " ++ show (addNumbers e f))

 Explication ligne par ligne

         addNumbers :: Num a => a -> a -> a

 La fonction accepte n’importe quel type a qui fait partie de la classe Num.

 Cela inclut : Int, Integer, Float, Double, etc.

           addNumbers x y = x + y

Retourne simplement la somme des deux arguments.

        let a = 5 :: Int
        let c = 3.5 :: Float
        let e = 100000000000 :: Integer

On spécifie les types pour tester différents cas (Int, Float, Integer).

         print ("addNumbers " ++ show a ++ " " ++ show b ++ " = " ++ show (addNumbers a b))

Affiche les résultats avec les valeurs utilisées.

 Résultat attendu à l’exécution

      "addNumbers 5 7 = 12"
      "addNumbers 3.5 2.0 = 5.5"
      "addNumbers 100000000000 1 = 100000000001"
