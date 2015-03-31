# install-ghc
Install GHC from source, using a binary distribution to bootstrap from, as non-root user.


## Step 1.

Make sure you have the following packages in your path.

* Basic development tools: `gcc`, `binutils`, etc.
* Python 2.7
* `fakechroot`


## Step 2.

Before starting, you may wish to remove any pre-existing Haskell packages.

```
rm ${HOME}/.ghc -rf
rm ${HOME}/.cabal -rf
```


## Step 3.

An example, installing into `${HOME}/install`.

```
cd install-ghc
./install-ghc --prefix=${HOME}/install --haskell-platform-archive ${ARCHIVES}/haskell-platform-2014.2.0.0-unknown-linux-x86_64.tar.gz --ghc-archive ${ARCHIVES}/ghc-7.8.4-src.tar.bz2
```

