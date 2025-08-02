HC1T2 - Tâche 2 : Exemple de fonction pure

 Objectif

    Écrire une fonction pure circleArea qui :

        prend un rayon r en paramètre,

        retourne l’aire du cercle (π × r²),

        ne dépend pas de l’état externe (aucune entrée/sortie ni variable globale).

 Correction complète avec main

-- Fichier : Main.hs

-- Calcule l'aire d'un cercle à partir du rayon
circleArea :: Floating a => a -> a
circleArea r = pi * r * r

-- Fonction principale pour tester
main :: IO ()
main = do
    let rayon = 3.0
    print ("Rayon du cercle       : " ++ show rayon)
    print ("Aire du cercle        : " ++ show (circleArea rayon))

 Explication ligne par ligne
circleArea :: Floating a => a -> a

    Type générique : fonctionne avec Float, Double, etc.

    Floating a : permet d’utiliser des nombres à virgule et pi.

    Elle prend un nombre r et retourne π × r².

circleArea r = pi * r * r

    pi est une constante prédéfinie en Haskell (3.14159265...)

    C’est une fonction pure car :

        elle ne lit rien d’extérieur,

        elle ne modifie rien,

        elle donne toujours le même résultat pour la même entrée.

main = do ...

    Définit une valeur rayon = 3.0

    Affiche le rayon et le résultat avec print + show.

 Résultat attendu à l'exécution

"Rayon du cercle       : 3.0"
"Aire du cercle        : 28.274333882308138"

