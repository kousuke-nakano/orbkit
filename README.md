# orbkit

**orbkit** is a **JAX-compatible** toolkit for continuous ab initio quantum Monte Carlo (QMC) simulations, developed entirely from scratch using `Python` and `JAX`. By leveraging `JAX` just-in-time (`jit`) compilation and vectorized mapping (`vmap`) functionalities, `orbkit` achieves high-performance computations **especially on GPUs** while remaining portable across CPUs, GPUs, and TPUs. See [here](http://jax.readthedocs.io/) for the details of `JAX`.

![license](https://img.shields.io/github/license/kousuke-nakano/orbkit)
![release](https://img.shields.io/github/release/kousuke-nakano/orbkit/all.svg)
![fork](https://img.shields.io/github/forks/kousuke-nakano/orbkit?style=social)
![stars](https://img.shields.io/github/stars/kousuke-nakano/orbkit?style=social)
![workflows](https://github.com/kousuke-nakano/orbkit/actions/workflows/orbkit-run-pytest.yml/badge.svg)

## How to install orbkit

First please git clone this repo.

```bash
% git clone https://github.com/kousuke-nakano/orbkit
```

**orbkit** can be installed via pip

```bash
% cd orbkit
% pip install .
```

> [!NOTE]
> `orbkit` is not yet distributed from `PyPI`. So, %pip install orbkit does not work at present.


## Examples
Examples are in `examples` directory.

## Documentation

**orbkit** user documentation is written using python sphinx. The source files are
stored in `doc` directory. Please see how to write the documentation at
`doc/README.md`.

## Contribution

Please see [CONTRIBUTING.md](CONTRIBUTING.md) for contribution guidelines.

## Develpment branch

The development of `orbkit` is managed on the `devel` branch of github `orbkit` repository.

- Github issues is the place to discuss about  `orbkit` issues.
- Github pull request is the place to request merging source code.

## Formatting

Formatting rules are written in `pyproject.toml`.

## pre-commit

Pre-commit (https://pre-commit.com/) is mainly used for applying the formatting
rules automatically. Therefore, it is strongly encouraged to use it at or before
git-commit. Pre-commit is set-up and used in the following way:

- Installed by `pip install pre-commit`, `conda install pre_commit` or see
  https://pre-commit.com/#install.
- pre-commit hook is installed by `pre-commit install`.
- pre-commit hook is run by `pre-commit run --all-files`.

Unless running pre-commit, pre-commit.ci may push the fix at PR by github
action. In this case, the fix should be merged by the contributor's repository.

## VSCode setting
- Not strictly, but VSCode's `settings.json` may be written like below

  ```json
  "ruff.lint.args": [
      "--config=${workspaceFolder}/pyproject.toml",
  ],
  "[python]": {
      "editor.defaultFormatter": "charliermarsh.ruff",
      "editor.codeActionsOnSave": {
          "source.organizeImports": "explicit"
      }
  },
  ```

## How to run tests

Tests are written using pytest. To run tests, pytest has to be installed.
The tests can be run by

```bash
% pytest -s -v  # with jax-jit
% pytest -s -v --disable-jit  # without jax jit
```
