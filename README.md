# A Jupyter Notebook Devcontainer for Golang

## The Motivation

When I was searching for simple interactive notebook to play with Go, I've realized that options are very limited.
The [Gophernotes](https://github.com/gopherdata/gophernotes) is the best option I was able to discover.
Still following features were missing for me out of the box:

- Cross platform (Intel and ARM)
- Must work with VSCode Jupyter extension
- Portable (that means it should work on any machine with Docker or in the cloud)

The devcontainer provided in this repository helps to address this requirements.

## How To Use

- Copy this repo by using `+ > Import Repository` on Github or fork it.
- Open this repository with VScode on any machine with Docker. `Remote Development` extension pack must be installed first.
- Open the repository in devcontainer.
- Create your notebook or open `test-go.ipynb`
- Select Go kernel.
- Enjoy!

> You can also run this devcontainer as Github Codespace by clicking `Code > Codespaces > Create codespace on master`. Check [GH Codespaces documentation](https://github.com/features/codespaces) first.

## Known Issues

The Jupyter VSCode extension is not displaying notebook content when opening a codespace with a notebook on iPad (Safari) or in [`Blink SSH` app](https://blink.sh/).
