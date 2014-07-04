lein-protobuf is a [Leiningen](https://github.com/technomancy/leiningen) plugin for compiling
[Google Protobuf](http://code.google.com/p/protobuf/) `.proto` files into Java `.class` files. It
can be used with or without [clojure-protobuf](https://github.com/flatland/clojure-protobuf), which
is a Clojure wrapper around the Java protobuf API.

## Why fork?

I forked from [the "official" version](https://github.com/flatland/lein-protobuf) from the original for a two key additions:

1. Allow for the use of an already installed version of protoc (the protocol buffer compiler).
2. Fix an issue with compiling protoc v2.4.1 on Mac OS X 10.9.

## Getting started

Add the following to your `project.clj` file:

    :plugins [[lein-protobuf "0.4.2-SNAPSHOT"]]

*Note: lein-protobuf requires at least version 2.0 of Leiningen.*

## Usage

By default, lein-protobuf looks for `.proto` files in `resources/proto` in your project
directory. This was chosen as the default location so that `.proto` files would also be included in
your jar files. You can change this with:

    :proto-path "path/to/proto"

You can also specify the Protocol Buffer version in your project file like so (defaults to version 2.5.0):

    :protobuf-version "2.4.1"

To compile all `.proto` files in this directory, just run:

    lein protobuf

You can also compile specific proto files with:

    lein protobuf file1.proto file2.proto

We also add a hook to Leiningen's `compile` task, so `.proto` files will automatically be compiled
before that task runs. So if you like, you can simply run:

    lein compile


## Getting Help

If you have any questions or need help, feel free to use the GitHub issues or reach out to me on Twitter: [@mikeflynn_](http://twitter.com/mikeflynn_).
