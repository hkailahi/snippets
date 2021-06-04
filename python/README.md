# Python

## Contents

- [Python](#python)
  - [Contents](#contents)
  - [From CLI](#from-cli)
    - [Build a virtualenv-style python environment from a `requirements.txt` (nix-shell)](#build-a-virtualenv-style-python-environment-from-a-requirementstxt-nix-shell)
  - [From REPL](#from-repl)
    - [Reload package in REPL](#reload-package-in-repl)
    - [See value's methods](#see-values-methods)

## From CLI

See [`mach-nix`](https://github.com/DavHau/mach-nix#build-a-virtualenv-style-python-environment-from-a-requirementstxt)

### Build a virtualenv-style python environment from a `requirements.txt` (nix-shell)

```
$ mach-nix env ./env -r requirements.txt
```

This will generate the python environment into ./env. To activate it, execute:

```
nix-shell ./env
```

The ./env directory contains a portable and reproducible definition of your python environment. To reuse this environment on another system, just copy the ./env directory and use nix-shell to activate it.

NOTE Foreign dependencies will need to be specified in `python.nix` (and removed from requirements file)

```nix
with (import ./inputs.nix);
let
pdfstructure = mach-nix.buildPythonPackage {
  src = builtins.fetchGit{
    url = "https://github.com/ChrizH/pdfstructure";
    ref = "master";
    rev = "1be97d954418b17d0d628ae6595c6aab54c7bd1c";
  };
};
in
mach-nix.mkPython {
  requirements = builtins.readFile ./requirements.txt;
  packagesExtra = [ pdfstructure ];
}
```

## From REPL

Following snippets from inside a `python` repl.

### Reload package in REPL

`importlib`

```python
>>> import importlib
>>> importlib.reload(<lib>)
```

### See value's methods

`dir`

```python
>>> dir(123)
['__abs__', '__add__', '__and__', '__bool__', '__ceil__', '__class__', '__delattr__', '__dir__', '__divmod__', '__doc__', '__eq__', '__float__', '__floor__', '__floordiv__', '__format__', '__ge__', '__getattribute__', '__getnewargs__', '__gt__', '__hash__', '__index__', '__init__', '__init_subclass__', '__int__', '__invert__', '__le__', '__lshift__', '__lt__', '__mod__', '__mul__', '__ne__', '__neg__', '__new__', '__or__', '__pos__', '__pow__', '__radd__', '__rand__', '__rdivmod__', '__reduce__', '__reduce_ex__', '__repr__', '__rfloordiv__', '__rlshift__', '__rmod__', '__rmul__', '__ror__', '__round__', '__rpow__', '__rrshift__', '__rshift__', '__rsub__', '__rtruediv__', '__rxor__', '__setattr__', '__sizeof__', '__str__', '__sub__', '__subclasshook__', '__truediv__', '__trunc__', '__xor__', 'bit_length', 'conjugate', 'denominator', 'from_bytes', 'imag', 'numerator', 'real', 'to_bytes']
```
