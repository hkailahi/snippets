# Contents
- [Contents](#contents)
  - [Get the version of nixpkgs](#get-the-version-of-nixpkgs)

## Get the version of nixpkgs

Basically checking what's `$HOME/default.nix`

```nix
$ nix-instantiate --eval -E '(import <nixpkgs> {}).lib.version'
"21.05pre284501.118485230c0"
```