Marginalia 0.9.1
================

[![Clojars Project](https://img.shields.io/clojars/v/marginalia.svg)](https://clojars.org/marginalia)

![marginalia](http://farm8.staticflickr.com/7057/6828224448_32b51e5784_z_d.jpg "Marginalia")

*Ultra-lightweight literate programming[1] for
[Clojure](http://clojure.org) and ClojureScript inspired by
[docco](http://jashkenas.github.com/docco/)*

Marginalia is a source code documentation tool that parses Clojure and
ClojureScript code and outputs a side-by-side source view with
appropriate comments and docstrings aligned.

To get a quick look at what the Marginalia output looks like, [visit
the official site](http://gdeer81.github.io/marginalia/).

**[View the release notes for this version of Marginalia](https://github.com/gdeer81/marginalia/blob/master/docs/release-notes/marginalia-v0.9.1-release-notes.markdown)**

# Usage

Currently Marginalia can be used in a number of ways as described below.

## deps.edn

To use Marginalia with deps.edn, add an alias like this:

```clojure
{:aliases {:docs {:extra-deps {marginalia {:git/url "https://github.com/wactbprot/marginalia" 
                                           :sha "1234"}}
                  :exec-fn marginalia.core/run-marginalia
                  :main-opts ["-m" "marginalia.core" "-n" "Projectname"]}}}
```

Marginalia accepts `:main-opts` as described below:

* -d --dir Directory into which the documentation will be written
  (default `docs`)
* -f --file File into which the documentation will be written (default
  `uberdoc.html`)
* -m --multi   Generate each namespace documentation as a separate file
* -n --name    Project name<sup>☆</sup>
* -v --version Project version<sup>☆</sup>
* -D --desc Project description<sup>☆</sup>
* -a --deps Project dependencies in the form
  `<group1>:<artifact1>:<version1>;<group2>...`<sup>☆</sup>
* -c --css Additional css resources `<resource1>;<resource2>;...`<sup>☆</sup>
* -j --js Additional javascript resources `<jsfile1>;<jsfile2>;...`<sup>☆</sup>
* -e --exclude Exclude source file(s) from the document generation
  process `<file1>;<file2>;...`<sup>☆</sup>

<sup>☆</sup> if not given will be taken from `project.clj` TODO:
extract information from `deps.edn`

## Maven

The [zi plugin](https://github.com/pallet/zi) supports Marginalia.

<details> <summary>Add this code to the project's `pom.xml` file, and
  run the command `mvn zi:marginalia`.</summary>

```xml
    <plugin>
      <groupId>org.cloudhoist.plugin</groupId>
      <artifactId>zi</artifactId>
      <version>0.5.0</version>
      <configuration>
        <marginaliaTargetDirectory>autodoc/marginalia</marginaliaTargetDirectory>
      </configuration>
    </plugin>
```

And the following to the project's `settings.xml` file.

```xml
    <pluginGroups>
      <pluginGroup>org.cloudhoist.plugin</pluginGroup>
    </pluginGroups>

    <profiles>
      <profile>
        <id>clojure-dev</id>
        <pluginRepositories>
          <pluginRepository>
            <id>sonatype-snapshots</id>
            <url>http://oss.sonatype.org/content/repositories/releases</url>
          </pluginRepository>
        </pluginRepositories>
      </profile>
    </profiles>

    <activeProfiles>
      <activeProfile>clojure-dev</activeProfile>
    </activeProfiles>
```
</details>

Contributors and thanks
-----------------------

I would like to thank Zachary Kim for taking a pile of incoherent code
and making it something worth using.  Marginalia would be nothing
without his hard work and vision.

I would also like to thank Justin Balthrop and Brenton Ashworth for
their support and code contributions.

Notes
-----

[1] While the phrase *ultra-lightweight literate programming* is used
to describe Marginalia, it is in no way a tool for classical literate
programming.  That is, Marginalia is a linear documentation generator
allowing no out-of-order reassembly of source.

Marginalia is...
----------------

*sorted by first commit*

- [Fogus](http://fogus.me/fun/)
- [Zachary Kim](https://github.com/zk)
- [Justin Balthrop](https://github.com/ninjudd)
- [Brenton Ashworth](https://github.com/brentonashworth)
- [Nicolas Buduroi](https://github.com/budu)
- [Michael Harrison](https://github.com/goodmike)
- [Anthony Grimes](https://github.com/Raynes)
- [Sam Ritchie](https://github.com/sritchie)
- [Hugo Duncan](https://github.com/hugoduncan)
- [Vadim](https://github.com/dm3)
- [Meikel Brandmeyer](https://github.com/kotarak)
- [Paul Dorman](https://github.com/pauldorman)
- [Deepak Giridharagopal](https://github.com/grimradical)
- [Tero Parviainen](https://github.com/teropa)
- [MerelyAPseudonym](https://github.com/MerelyAPseudonym)
- [Ivan](https://github.com/ivantm)
- [Benjamin Bader](https://github.com/benjamin-bader)
- [Frederick Giasson](https://github.com/fgiasson)
- [Michael Bloom](https://github.com/MichaelBlume)
- [Tristan Strange](https://github.com/triss)
If I've missed your name then please ping me.

License
-------

Copyright (C) 2010-2017 Gary, Fogus and contributors.

Distributed under the Eclipse Public License, the same as Clojure.
