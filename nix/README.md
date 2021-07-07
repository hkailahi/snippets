# Contents
- [Contents](#contents)
  - [Try library in \<LANGUAGE\>](#try-library-in-language)
    - [Haskell](#haskell)
    - [Python](#python)
  - [Get the version of nixpkgs](#get-the-version-of-nixpkgs)

## Try library in \<LANGUAGE\>

Spin up environment with `nix-shell -p "<lang>.withPkgs (pkgs: with pkgs; [ <pkg1> <pkg2> <...> ])`

### Haskell

Example

```shell
$ nix-shell -p "ghc.withPkgs (pkgs: with pkgs; [ newtype ])"
...
[nix-shell]$ ghci
...
λ> import Control.Newtype
```

### Python

Example

```shell
$ nix-shell -p "python37.withPkgs (pkgs: with pkgs; [ pandas ])"
...
[nix-shell]$ python
...
>>> import pandas
```

## Get the version of nixpkgs

Basically checking what's `$HOME/default.nix`

```nix
$ nix-instantiate --eval -E '(import <nixpkgs> {}).lib.version'
"21.05pre284501.118485230c0"
```