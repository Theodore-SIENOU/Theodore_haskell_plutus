

# HC2T1 - Tâche 1 : Vérification des types dans GHCi

## Objectif

Prédire et vérifier dans **GHCi** les types de valeurs de base.
On utilise `:t` dans GHCi pour obtenir le type d’une expression.

## Types attendus

1. `42`

   * Attendu : `Int` (un entier simple).

2. `3.14`

   * Attendu : `Float` ou `Double` (un nombre à virgule).

3. `"Haskell"`

   * Attendu : `String` (une chaîne de caractères).

4. `'Z'`

   * Attendu : `Char` (un seul caractère).

5. `True && False`

   * Attendu : `Bool` (opération logique → retourne un booléen).

## Vérification dans GHCi

Dans GHCi, on tape :

```haskell
Prelude> :t 42
42 :: Int

Prelude> :t 3.14
3.14 :: Double   -- GHCi choisit Double par défaut

Prelude> :t "Haskell"
"Haskell" :: String

Prelude> :t 'Z'
'Z' :: Char

Prelude> :t True && False
True && False :: Bool
```

## Explication ligne par ligne

* `42 :: Int` → valeur entière de type `Int`.
* `3.14 :: Double` → nombre à virgule, par défaut en `Double` dans GHCi.
* `"Haskell" :: String` → une chaîne est une **liste de Char**, mais GHCi l’affiche comme `String`.
* `'Z' :: Char` → caractère unique de type `Char`.
* `True && False :: Bool` → opération booléenne entre deux `Bool`, résultat `Bool`.

## Résultat attendu

```
42 :: Int
3.14 :: Double
"Haskell" :: String
'Z' :: Char
True && False :: Bool
```
