# Fast binary serialisation and CBOR implementation for Haskell

[![Linux Build Status](https://img.shields.io/travis/well-typed/cborg/master.svg?label=Linux%20build)](https://travis-ci.org/well-typed/cborg)
[![Windows Build Status](https://img.shields.io/appveyor/ci/thoughtpolice/cborg/master.svg?label=Windows%20build)](https://ci.appveyor.com/project/thoughtpolice/cborg/branch/master)
[![Hackage cborg version](https://img.shields.io/hackage/v/cborg.svg?label=Hackage)](https://hackage.haskell.org/package/cborg)
[![Hackage serialise version](https://img.shields.io/hackage/v/serialise.svg?label=Hackage)](https://hackage.haskell.org/package/serialise)
[![Stackage cborg version](https://www.stackage.org/package/cborg/badge/lts?label=Stackage)](https://www.stackage.org/package/cborg)
[![Stackage serialise  version](https://www.stackage.org/package/serialise/badge/lts?label=Stackage)](https://www.stackage.org/package/serialise)
[![BSD3](https://img.shields.io/badge/License-BSD-blue.svg)](https://en.wikipedia.org/wiki/BSD_License)
[![Haskell](https://img.shields.io/badge/Language-Haskell-yellowgreen.svg)](https://www.haskell.org)

This repo contains two libraries (plus associated tools):

The `serialise` library is for serialising Haskell values and deserialising
them later.

The `cborg` library provides a fast, standards-compliant implementation of the
'Concise Binary Object Representation' (specified in `RFC 7049`) for Haskell.

The `serialise` library uses the CBOR format, via the `cborg` library, which
gives it the following benefits:

 * fast serialisation and deserialisation
 * compact binary format
 * stable format across platforms (32/64bit, big/little endian)
 * support for backwards compatible deserialisation with migrations
 * the ability to inspect binary values with generic tools,
   e.g. for debugging or recovery, including generic conversion into JSON text
 * potential to read the serialised format from other languages
 * incremental or streaming (de)serialisation
 * internal message framing (for use in network application)
 * suitable to use with untrusted input (resistance to asymmetric resource
   consumption attacks)


# Installation

They are just a `cabal install` away on [Hackage][], or through [Stackage][]:

```bash
$ cabal install cborg serialise
$ stack install cborg serialise
```

There are also a few related packages that you may be interested in:

 * `cborg-json` implements the bijection between JSON and CBOR specified in the RFC.
 * `cbor-tool` is a handy command-line utility for working with CBOR data.

[Hackage]:  https://hackage.haskell.org/package/cborg
[Stackage]: https://www.stackage.org

# Join in

Be sure to read the [contributing guidelines][contribute]. File bugs
in the GitHub [issue tracker][].

Master [git repository][gh]:

* `git clone https://github.com/well-typed/cborg.git`

The tests for the `cborg` package are currently included in the `serialise`
package.

```bash
$ cabal test serialise
$ stack test serialise
```

Note: the `stack.yaml` file is currently synchronized to **LTS-8.13**. Further
compilers and other LTS releases are currently not supported with Stack at the
moment, but the build *is* tested with older compilers and Cabal libraries
(through Travis CI).

[contribute]: https://github.com/well-typed/cborg/blob/master/.github/CONTRIBUTING.md
[issue tracker]: http://github.com/well-typed/cborg/issues
[gh]: http://github.com/well-typed/cborg

# Authors

See
[AUTHORS.txt](https://raw.github.com/well-typed/cborg/master/AUTHORS.txt).

# License

BSD3. See
[LICENSE.txt](https://raw.github.com/well-typed/cborg/master/LICENSE.txt)
for the exact terms of copyright and redistribution.
