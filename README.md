# FlameCoin Core [FLA, ₣]
==========================

<a href="https://ibb.co/gPL977"><img src="https://preview.ibb.co/ipDkfS/105695_OMLJSE_613.png" alt="105695_OMLJSE_613" border="0"></a>

[![Build Status](https://travis-ci.org/flamecoin/flamecoin.svg)](https://travis-ci.org/flamecoin/flamecoin)

## What is Flamecoin?
Flamecoin is a cryptocurrency like Bitcoin, although it does not use SHA256 as its proof of work (POW). Taking development cues from Tenebrix and litecoin, Flamecoin currently employs a simplified variant of scrypt. (Flame coin is forked from litecoin)

## Social Media:
- **Reddit:** https://reddit.com/r/flamecoincrypto

- **Telegram Chat:** http://t.me/flamecoin

- **Discord:** https://discord.gg/HnZt6Pm


## License
Flamecoin is released under the terms of the MIT license. See [COPYING](COPYING)
for more information or see http://opensource.org/licenses/MIT.

## Development and contributions
Development is ongoing, and the development team, as well as other volunteers, can freely work in their own trees and submit pull requests when features or bug fixes are ready.

#### Version strategy
Version numbers are following ```major.minor.patch``` semantics.

#### Branches
There are a few types of branches in this repository:

- **master:** Stable, contains the latest version of the latest *major.minor* release.
- **maintenance:** Stable, contains the latest version of previous releases, which are still under active maintenance. Format: ```<version>-maint```
- **development:** Unstable, contains new code for planned releases. Format: ```<version>-dev```

*Master and maintenance branches are exclusively mutable by release. Planned releases will always have a development branch and pull requests should be submitted against those. Maintenance branches are there for* ***bug fixes only,*** *please submit new features against the development branch with the highest version.*

## Frequently Asked Questions:

 - Where can I download a working build?
 
 Under the releases page on github the latest binarys can be found.
 
 - ITS NOT WORKING!
 
 If its broken, submit an issue. (https://github.com/flamecoin/flamecoin/issues)
 


### How to build yourself:

  The following are developer notes on how to build flamecoin on your native platform. They are not complete guides, but include notes on the necessary libraries, compile flags, etc.

  - [OSX Build Notes](doc/build-osx.md)
  - [Unix/Linux Build Notes](doc/build-unix.md)
  - [Windows Build Notes](doc/build-msw.md)

### Ports
9333 (Maybe 9342 soon)

RPC 22555



Translations
------------

Changes to translations, as well as new translations, can be submitted to
[Bitcoin Core's Transifex page](https://www.transifex.com/projects/p/bitcoin/).

Periodically the translations are pulled from Transifex and merged into the git repository. See the
[translation process](doc/translation_process.md) for details on how this works.

If the changes are Flamecoin specific, they can be submitted as pull requests against this repository.
If it is a general translation, consider submitting it through upstream, as we will pull these changes later on.

Development tips and tricks
---------------------------

**compiling for debugging**

Run configure with the --enable-debug option, then make. Or run configure with
CXXFLAGS="-g -ggdb -O0" or whatever debug flags you need.

**debug.log**

If the code is behaving strangely, take a look in the debug.log file in the data directory;
error and debugging messages are written there.

The -debug=... command-line option controls debugging; running with just -debug will turn
on all categories (and give you a very large debug.log file).

The Qt code routes qDebug() output to debug.log under category "qt": run with -debug=qt
to see it.

**testnet and regtest modes**

Run with the -testnet option to run with "play flamecoins" on the test network, if you
are testing multi-machine code that needs to operate across the internet.

If you are testing something that can run on one machine, run with the -regtest option.
In regression test mode, blocks can be created on-demand; see qa/rpc-tests/ for tests
that run in -regtest mode.

**DEBUG_LOCKORDER**

Flamecoin Core is a multithreaded application, and deadlocks or other multithreading bugs
can be very difficult to track down. Compiling with -DDEBUG_LOCKORDER (configure
CXXFLAGS="-DDEBUG_LOCKORDER -g") inserts run-time checks to keep track of which locks
are held, and adds warnings to the debug.log file if inconsistencies are detected.

**Thanks to:**

Paul DeCarlo (Github: toolboc) **For making the Tutorial
 to make an altcoin** http://hackster.io/pjdecarlo/how-to-make-a-cryptocurrency-using-litecoin-v0-15-source-fb5e82
