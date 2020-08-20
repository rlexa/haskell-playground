# haskell-playground

I don't know, Haskell sounded interesting.

## Project Creation

The following steps were taken to create the environment etc.

1. Install `stack` https://get.haskellstack.org/stable/windows-x86_64-installer.exe
   1. `stack install intero QuickCheck` for a global installation
   2. `stack build intero QuickCheck` for a local installation
   3. `stack install hlint` for beginner linting
2. Install VS Code
   1. Extension: https://marketplace.visualstudio.com/items?itemName=UCL.haskelly
   2. Extension: https://github.com/hoovercj/vscode-haskell-linter

### GHCi

`load GHCi` loads current file with context, good for testing it's functions. Typing `:r` reloads context.

`stack exec ghcid YOUR_FILE_NAME.hs` runs ghcid.