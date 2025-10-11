### **HC9T7 - Tâche 7 : Fonction pour calculer l’engagement**

#### **Sujet**

> Créer une fonction `engagement` qui calcule l’engagement d’un `Tweet`
> en sommant ses **likes** et l’engagement de tous ses **commentaires**.

---

###  **Correction complète**

```haskell
-- Fichier : Main.hs

-- Définition du type récursif Tweet
data Tweet = Tweet
    { content  :: String
    , likes    :: Int
    , comments :: [Tweet]
    } deriving (Show)

-- Fonction engagement : calcule le total des likes (tweet + commentaires)
engagement :: Tweet -> Int
engagement (Tweet _ l cs) = l + sum (map engagement cs)

-- Exemple de tweets
tweet1 :: Tweet
tweet1 = Tweet
    { content = "Hello Haskell world!"
    , likes = 10
    , comments =
        [ Tweet { content = "Nice post!", likes = 3, comments = [] }
        , Tweet { content = "Welcome to FP!", likes = 5, comments =
            [ Tweet { content = "FP rocks!", likes = 2, comments = [] } ]
          }
        ]
    }

main :: IO ()
main = do
    print tweet1
    putStrLn ("Engagement total : " ++ show (engagement tweet1))
```

---

### **Explication**

* `engagement` est une **fonction récursive** :

  * Elle additionne les `likes` du tweet courant (`l`)
  * Puis elle applique `engagement` à chaque tweet dans la liste des `comments`
  * Le tout est additionné avec `sum` et `map`

Formule :

```haskell
engagement (Tweet _ l cs) = l + sum (map engagement cs)
```

* `map engagement cs` → applique la fonction `engagement` à chaque commentaire
* `sum` → additionne tous les résultats

---

### **Résultat à l’exécution**

```
Tweet
  { content = "Hello Haskell world!"
  , likes = 10
  , comments =
      [ Tweet {content = "Nice post!", likes = 3, comments = []}
      , Tweet
          { content = "Welcome to FP!"
          , likes = 5
          , comments = [Tweet {content = "FP rocks!", likes = 2, comments = []}]
          }
      ]
  }
"Engagement total : 20"
```

---
