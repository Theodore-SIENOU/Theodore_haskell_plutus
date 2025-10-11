### **HC7T7 – Utiliser `Bounded` et `Enum`**

**Sujet :**
Créer une fonction `nextColor` qui prend une `Color` et retourne la couleur suivante dans l’ordre.
Si c’est la dernière couleur, elle doit revenir à la première.

---

###  **Correction complète**

```haskell
-- Définition du type Color
data Color = Red | Green | Blue
    deriving (Show, Enum, Bounded, Eq)

-- Fonction nextColor : passe à la couleur suivante ou revient à la première
nextColor :: Color -> Color
nextColor c
    | c == maxBound = minBound
    | otherwise     = succ c

-- Fonction principale pour tester
main :: IO ()
main = do
    print $ nextColor Red    -- Green
    print $ nextColor Green  -- Blue
    print $ nextColor Blue   -- Red
```

---

###  **Explication**

* `Enum` permet d’utiliser `succ` (successeur) et `pred` (prédécesseur) sur `Color`.
* `Bounded` fournit `minBound` et `maxBound` pour savoir respectivement la première et la dernière couleur.
* Si `c` est la dernière couleur (`maxBound`), on retourne `minBound`.
* Sinon, on retourne la couleur suivante avec `succ`.

---

###  **Résultat attendu à l’exécution**

```
Green
Blue
Red
```
