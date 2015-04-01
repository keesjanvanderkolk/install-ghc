# install-ghc
Install GHC from source, using a binary distribution to bootstrap from, as non-root user, on Linux.

See the `other` directory for more tools.


## Step 1.

Download the Haskell platform binary archive, and the GHC sources. In our example, we use the following files.

```
haskell-platform-2014.2.0.0-unknown-linux-x86_64.tar.gz 
ghc-7.8.4-src.tar.bz2
```


## Step 2.

Make sure you have the following packages in your path.

* Basic development tools: `gcc`, `binutils`, etc.
* Python 2.7 (or compatible version)
* `fakechroot`


## Step 3.

Before starting, you may wish to remove any pre-existing Haskell packages.

```
rm ${HOME}/.ghc -rf
rm ${HOME}/.cabal -rf
```


## Step 4.

An example, installing into `${HOME}/install`.

```
cd install-ghc
./install-ghc --prefix=${HOME}/install --haskell-platform-archive ${ARCHIVES}/haskell-platform-2014.2.0.0-unknown-linux-x86_64.tar.gz --ghc-archive ${ARCHIVES}/ghc-7.8.4-src.tar.bz2
```


## Notes

The script uses a fake chroot environment to install the Haskell platform (from which a final verion of GHC will be built). This chroot environment is populated with files from the `/usr` folder, and as such it can become quite large.

Also, the script assumes that the target prefix will reside inside the `/home` tree. If this is not the case, then it will be necessary to edit the script.


## Step 5 (optional).

Install Cabal (the library and the tool).

```
wget "https://www.haskell.org/cabal/release/cabal-1.22.2.0/Cabal-1.22.2.0.tar.gz"
./install-Cabal --prefix=${HOME}/install-h --Cabal-archive Cabal-1.22.2.0.tar.gz

wget "https://www.haskell.org/cabal/release/cabal-install-1.22.2.0/cabal-install-1.22.2.0.tar.gz"
./install-cabal-install --prefix=${HOME}/install-h --cabal-install-archive cabal-install-1.22.2.0.tar.gz 
```
