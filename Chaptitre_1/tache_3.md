HC1T3 - Tâche 3 : Vérifier si un nombre est supérieur à 18

 Objectif

    Écrire une fonction greaterThan18 qui :

        prend un nombre en paramètre,

        retourne True si ce nombre est strictement supérieur à 18, sinon False,

        doit être pure (pas d'entrée/sortie, toujours même résultat pour la même entrée).

 Correction complète avec main

       -- Fichier : Main.hs
       -- Vérifie si un nombre est supérieur à 18
       greaterThan18 :: (Ord a, Num a) => a -> Bool
       greaterThan18 x = x > 18

       -- Fonction principale pour tester
       main :: IO ()
       main = do
           let a = 12
           let b = 18
           let c = 25
           print ("greaterThan18 " ++ show a ++ " = " ++ show (greaterThan18 a))
           print ("greaterThan18 " ++ show b ++ " = " ++ show (greaterThan18 b))
           print ("greaterThan18 " ++ show c ++ " = " ++ show (greaterThan18 c))

 Explication ligne par ligne
 
      greaterThan18 :: (Ord a, Num a) => a -> Bool
      
 Num a : a doit être un type numérique (Int, Float, etc.).
 Ord a : a doit pouvoir être comparé avec > (ordre).
 La fonction retourne un Booléen : True ou False.

     greaterThan18 x = x > 18

Si x est strictement plus grand que 18, alors True
Sinon, False

    main = do ...

Teste la fonction avec plusieurs valeurs (12, 18, 25)
Utilise print avec show pour bien afficher les résultats

 Résultat attendu à l'exécution

     "greaterThan18 12 = False"
     "greaterThan18 18 = False"
     "greaterThan18 25 = True"

