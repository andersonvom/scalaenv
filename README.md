scalaenv
====

[![Build Status](https://travis-ci.org/scalaenv/scalaenv.svg?branch=master)](https://travis-ci.org/scalaenv/scalaenv)

Groom your app's Scala environment with scalaenv like [rbenv](https://github.com/sstephenson/rbenv) :)

Do you need [**sbt**](http://www.scala-sbt.org) version management?  
Please refer to [**sbtenv**](https://github.com/sbtenv/sbtenv) in the case of use **sbt**.

### Installation

#### Basic GitHub Checkout

1. `git clone` scalaenv into `~/.scalaenv`.

    ~~~ sh
    $ git clone git://github.com/scalaenv/scalaenv.git ~/.scalaenv
    ~~~

    Optionally, try to compile dynamic bash extension to speed up scalaenv. Don't worry if it fails; scalaenv will still work normally:

    ~~~sh
    cd ~/.scalaenv && src/configure && make -C src
    ~~~

2. Add `~/.scalaenv/bin` to your `$PATH` for access to the `scalaenv` command.

    ~~~ sh
    $ echo 'export PATH="${HOME}/.scalaenv/bin:${PATH}"' >> ~/.zshrc
    ~~~

3. Add `scalaenv init` to your shell to enable shims and autocompletion.

    ~~~ sh
    $ echo 'eval "$(scalaenv init -)"' >> ~/.zshrc
    ~~~

    **Bash note**: Modify your `~/.bash_profile` file instead of `~/.zshrc`.

4. Restart your shell so that PATH changes take effect. (Opening a new
   terminal tab will usually do it.) Now check if scalaenv was set up:

    ~~~ sh
    $ type scalaenv
    #=> "scalaenv is a shell function"
    ~~~

    *Same as in previous step, use `~/.bash_profile` for Bash.*

5. Install each version of scala.

    ~~~ sh
    $ scalaenv install scala-2.10.3
    ~~~

    If show all available version, please use the following command:

    ~~~ sh
    $ scalaenv install -l
    All available versions:
    scala-2.10.1
    scala-2.10.2
    scala-2.10.3
    ...
    ~~~

    If want to install manually, please download scala archive and extract into `~/.scalaenv/versions/`.

    ~~~ sh
    $ curl -LO http://www.scala-lang.org/files/archive/scala-2.10.3.tgz
    $ tar xf scala-2.10.3.tgz -C ~/.scalaenv/versions/
    ~~~

#### Homebrew on Mac OSX

As an alternative to installation via GitHub checkout, you can install scalaenv using the [Homebrew package manager](http://brew.sh) on Mac OSX.

~~~ sh
$ brew update
$ brew install scalaenv
~~~

Or, if you would like to install the latest development release:

~~~sh
$ brew install --HEAD scalaenv
~~~

To upgrade HEAD package use `--fetch-HEAD` option:

~~~sh
$ brew upgrade --fetch-HEAD scalaenv
~~~

### Version History

**0.0.14** (Jul 28, 2017)
  * Added **dotty-0.2.0-RC1**
  * Supported for fish shell :tada: 
    * https://github.com/scalaenv/scalaenv/pull/44

**0.0.13** (Jun 25, 2017)
  * dotty support :tada:
    ~~~sh
    scalaenv install dotty-0.1.2-RC1
    scalaenv global dotty-0.1.2-RC1-bin-SNAPSHOT
    scalaenv rehash
    dotr
    ~~~

**0.0.12** (Apr 24, 2017)
  * Added **Scala 2.11.9** - **Scala 2.11.11** , **Scala 2.12.2** - **Scala 2.13.0-M1**.
    Thanks to @Kaioru..

**0.0.11** (Feb 03, 2017)
  * Added **Scala 2.12.1**.
    Thanks to @3tty0n.

**0.0.10** (Dec 05, 2016)

  * Added **Scala 2.11.8**, **Scala 2.12.0-M4** - **2.12.0**.
    Thanks to @odd, @3tty0n

**0.0.9** (Jan 06, 2016)

  * Added **Scala 2.12.0-M3** and more Scala 2.10 versions.
    Thanks to @joprice

**0.0.8** (Aug 25, 2015)

  * Added **Scala 2.11.5** - **Scala 2.11.7**, **Scala 2.12.0-M1** - **2.12.0-M2**  
    Many thanks to @alexanderscott, @tdstein, @rwinzhang

**0.0.7** (Nov 19, 2014)

  * Added recipes for **Scala 2.11.1** - **Scala 2.11.4** by @zaneli
  * Fixed a bug when run `versions` subcommand.

**0.0.6** (Apr 18, 2014)

  * Added recipes for **Scala 2.11.0** to *scala-install* built-in plugin.

**0.0.5** (Apr 16, 2014)

  * Added recipes for **Scala 2.10.4** and **Scala 2.11.0-RCx** to *scala-install* built-in plugin.
  * Added recipes for *old versions* to *scala-install* built-in plugin.

**0.0.4** (Mar 25, 2014)

  * Improved installation instruction by *scala-install* built-in plugin.

**0.0.3** (Mar 14, 2014)

  * Added [Travis CI](https://travis-ci.org) status badge on README.
  * Fixed a bug when run `rehash` subcommand.
  * Fixed version string.

**0.0.2** (Mar 04, 2014)

  * Added completions for `Z shell` and `Bash`.

**0.0.1** (Jan 28, 2014)

  * Initial public release.
