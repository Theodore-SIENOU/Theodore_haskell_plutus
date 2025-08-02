HC1T4 - Tâche 4 : Composer une fonction pour traiter des données de joueurs

 Objectif

Écrire une fonction getTopThreePlayers qui :

    prend une liste de tuples (nom, score)

    trie cette liste par score décroissant

    retourne les trois meilleurs joueurs avec leur score

    doit être pure (pas d’entrée/sortie)

 Correction complète avec main

        -- Fichier : Main.hs
        
        import Data.List (sortBy)
        
        -- Trie la liste par score décroissant
        sortByScore :: [(String, Int)] -> [(String, Int)]
        sortByScore = sortBy (\(_, s1) (_, s2) -> compare s2 s1)
        
        -- Prend les 3 premiers éléments
        topThree :: [(String, Int)] -> [(String, Int)]
        topThree = take 3
        
        -- Fonction composée : trie, puis prend le top 3
        getTopThreePlayers :: [(String, Int)] -> [(String, Int)]
        getTopThreePlayers = topThree . sortByScore
        
        -- Fonction principale pour tester
        main :: IO ()
        main = do
            let joueurs = [("Alice", 30), ("Bob", 45), ("Charlie", 25), ("David", 50), ("Eve", 35)]
            
            putStrLn "Liste initiale :"
            print joueurs
        
            putStrLn "\nTop 3 joueurs (nom, score) :"
            print (getTopThreePlayers joueurs)

 Explication ligne par ligne

sortBy (\(_, s1) (_, s2) -> compare s2 s1)

    Trie les joueurs en comparant les scores (s2 d'abord pour décroissant).

take 3

    Garde les 3 premiers éléments de la liste triée.

getTopThreePlayers = topThree . sortByScore

    Compose les deux fonctions pour :

        Trier les joueurs par score.

        En extraire les trois meilleurs.

main = do ...

    Crée une liste de joueurs.

    Affiche la liste originale.

    Affiche le top 3 avec nom et score.

 Résultat attendu à l’exécution

        Liste initiale :
        [("Alice",30),("Bob",45),("Charlie",25),("David",50),("Eve",35)]
        
        Top 3 joueurs (nom, score) :
        [("David",50),("Bob",45),("Eve",35)]
