# play1-cli

This is a **work in progress** and **proof of concept** port of the [Play1](https://github.com/playframework/play1) CLI tool to Python 3.

Besides that the Python code is ported, it also contains the following changes:

* Dependencies are managed with the [Gradle build tool](https://gradle.org/)
  * The `build.gradle` file contains the dependecy information (some comments on what's lacking)
  * Dependencies are split in those going into `framework/lib` and into `modules/testrunner/firephoque`
  * **NOTE:** The [patches](https://github.com/playframework/play1/tree/master/framework/patches) are not applied

The goal of this project is to provide a proof of concept for:

* a port of Play1's `play` CLI tool to Python 3
* a more modern way to install the `play` CLI tool
* a way to not have loads of vendor code (JARs, JS files, etc) in the source tree
* using Gradle (over Ivy) to manage dependencies where possible
* using Gradle (over Ant) as a generic build tool


## Installing

    git clone https://github.com/Stager-Software/play1-cli.git

Now move into the repo folder and do:

    ./gradlew getFrameworkDeps
    ./gradlew getFirephoqueDeps

You should now be able to use the `play` command as you are used to:

    ./play run ../myPlayProject

For more information see the documentation of the [Play1](https://github.com/playframework/play1) project.


## TODOs

* Extend the `build.gradle` file so it also handles:
  * Building the `play-x.y.z.jar` and the module JARs in `modules/*/lib`
  * The patching process that is currently not in place yet
  * Remove more vendor libs (jQuery, Selenium) out of the source tree: download and extract them with Gradle
* Make this project easily installable with `pip`
* There is [some clever Ivy stuff](https://github.com/playframework/play1/blob/master/framework/dependencies.yml) happening in Play1 that we do not have (setting up local repos, etc)


## Licence and contributing

Since this forks Play1, the license is kept the same with Play1.

Play1 framework is distributed under the [Apache 2.0 licence](http://www.apache.org/licenses/LICENSE-2.0.html), unless otherwise specified this is the license for all files in this repository.

In case you want to improve upon the project: fork it, commit changes to your branch, open a pull request. Thanks in advance.

For filing bugs, feature request or just asking questions you may use the issue tracker of [this project on Github](https://github.com/Stager-Software/play1-cli).

