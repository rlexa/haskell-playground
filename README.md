# haskell-playground

I don't know, Haskell sounded interesting.

## Knowhow

#### ghci

- playground cli, can be started with a file to load functions from it
- use `:r` to reload file
- use let keyword i.e. `let a = 3` to define something inside of ghci

#### Functions

- define with `sumUs x y = x + y`, name has to be lowercase
- call syntax is `sumUs 1 2` => 3
- calling a function has highest precedence i.e. `succ 9 * 10` => 100, `succ (9 * 10)` => 91
- functions with 2 args can have infix syntax i.e. `div 3 2` is the same as `` 3 `div` 2 ``
- functions without parameters are basically constants e.g. `myName = "Alex"` i.e. `myName` => "Alex"

#### Logic Statements

- use `doubleUnder100 x = (if x > 100 then x else x * 2)`
- always has `then` as well as `else` because everything must be an expression (return a value)

#### Lists

- lists are homogenous i.e. must have same type for every value
- strings `"like this"` are just sugar for a char list
- concatenate lists with `"hello " ++ "world"`
  - (!) bad performance with big lists
- cons operator (prepend elem to list) with `'h' : "ello"` => "hello"
  - (!) instant performance
  - `[1,2,3]` is actually sugar for `1:2:3:[]`
- index operator with `"hello" !! 1` => 'e'
- compare is possible if elements can be compared (lexigraphical) i.e. `[3,1,2] > [2,4,5]` => True
- create ranges with `[1..4]` => [1,2,3,4] or with steps `[3,6..10]` => [3,6,9]
  - (i) backward ranges `[4..1]` => [] but `[4,3..1]` => [4,3,2,1]
  - (i) infinite ranges `take 4 [2,4..]` => [2,4,6,8]

// @todo: http://learnyouahaskell.com/starting-out 'cycle'

### Existing Functions

#### Lists

| function             | example                      | fyi                                |
| -------------------- | ---------------------------- | ---------------------------------- |
| `head`, `last`       | `head [1,2,3]` => 1          | first/last list element            |
| `tail`, `init`       | `tail [1,2,3]` => [2,3]      | list without first/last element    |
| `length`             | `length [1,2,3]` => 3        |                                    |
| `null`               | `null []` => True            | check if empty                     |
| `reverse`            | `reverse [1,2,3]` => [3,2,1] |                                    |
| `take`               | `take 2 [1,2,3]` => [1,2]    | takes from beginning               |
| `drop`               | `drop 2 [1,2,3]` => [3]      | drops from beginning               |
| `maximum`, `minimum` | `maximum [1,2,3]` => 3       | finds max/min element if orderable |
| `sum`, `product`     | `sum [1,2,3]` => 6           | sum/product of list of numbers     |
| `elem`               | `elem 2 [1,2,3]` => True     | checks whether element in list     |

### Math

| function     | example        | fyi               |
| ------------ | -------------- | ----------------- |
| div          | `div 3 2` => 1 | integral division |
| `max`, `min` | `max 1 2` => 2 |                   |

### Misc

| function | example       | fyi       |
| -------- | ------------- | --------- |
| succ     | `succ 1` => 2 | successor |

## Project Creation

The following steps were taken to create the environment etc. (https://dev.to/egregors/vscode-for-haskell-in-2020-5dn8). That didn't work the way the author thought it would; the ghci stuff is only startable via stack here instead of directly in prompt.

1. Install `stack` https://get.haskellstack.org/stable/windows-x86_64-installer.exe
   1. `stack install intero QuickCheck` for a global installation
   2. `stack build intero QuickCheck` for a local installation
   3. `stack install hlint` for beginner linting
   4. `stack install ghcid` for ghci but with watch and reload
   5. `stack install brittany` for formatter
2. Install VS Code
   1. Extension: https://marketplace.visualstudio.com/items?itemName=UCL.haskelly
   2. Extension: https://github.com/hoovercj/vscode-haskell-linter
   3. Extension: haskell-ghcid
   4. Extension: https://github.com/MaxGabriel/brittany-vscode-extension

### GHCi

`load GHCi` loads current file with context, good for testing it's functions. Typing `:r` reloads context.

`stack exec ghcid YOUR_FILE_NAME.hs` runs ghcid.
