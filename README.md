# install-ghc
Install GHC from source, using a binary distribution to bootstrap from, as non-root user.

rm ${HOME}/.ghc
rm ${HOME}/.cabal

./install-ghc --prefix=${HOME}/install --haskell-platform-archive ${ARCHIVES}/haskell-platform-2014.2.0.0-unknown-linux-x86_64.tar.gz --ghc-archive ${ARCHIVES}/ghc-7.8.4-src.tar.bz2

