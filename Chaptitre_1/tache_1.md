HC1T1 - Tâche 1 : Composition de fonctions

 Sujet

    Composition de fonctions

        double : multiplie un nombre par 2

        increment : ajoute 1 à un nombre

        doubleThenIncrement : applique d’abord double, puis increment, en utilisant la composition de fonctions

 Correction complète (avec print)

-- Fichier : Main.hs

-- Multiplie un nombre entier par 2
double :: Int -> Int
double x = x * 2

-- Incrémente un nombre entier de 1
increment :: Int -> Int
increment x = x + 1

-- Applique double PUIS increment (composition de fonctions)
doubleThenIncrement :: Int -> Int
doubleThenIncrement = increment . double

-- Fonction principale : teste les fonctions avec print
main :: IO ()
main = do
    let x = 4
    print ("Valeur de depart : " ++ show x)
    print ("double x = " ++ show (double x))
    print ("increment x = " ++ show (increment x))
    print ("doubleThenIncrement x = " ++ show (doubleThenIncrement x))

 Explication
double :: Int -> Int

    Déclare une fonction qui prend un Int et retourne x * 2

increment :: Int -> Int

    Ajoute simplement 1 à l'entrée

doubleThenIncrement = increment . double

    Applique la composition de fonctions
    Cela signifie : doubleThenIncrement x = increment (double x)

main :: IO ()

    Point d'entrée du programme.
    Utilise print pour afficher les résultats dans le terminal, avec des show pour convertir les nombres en texte.

 Résultat à l'exécution

"Valeur de depart : 4"
"double x = 8"
"increment x = 5"
"doubleThenIncrement x = 9"
