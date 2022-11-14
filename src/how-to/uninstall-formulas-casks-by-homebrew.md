# Uninstall all formulas/casks installed by homebrew

## Uninstall all formulas
```sh
brew remove --force $(brew list --formula)
```

## Uninstall all casks
```sh
brew remove --cask --force $(brew list)
```

## Cleanup
```sh
brew autoremove && brew cleanup --prune=all
```
