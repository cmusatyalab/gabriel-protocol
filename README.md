# Updating Protocol

You should use version 3.0 of the protobuf compiler. You can find instructions
to download a binary of this version of the compiler
[here](https://github.com/tensorflow/models/blob/master/research/object_detection/g3doc/installation.md#manual-protobuf-compiler-installation-and-usage).
The compiler takes a while to build, so I recommend downloading a binary instead
of compiling it yourself.

You can then compile `gabriel.proto` by running the following lines:
1. `/path/to/protoc --python_out=python/src/gabriel_protocol/ gabriel.proto`
2. `/path/to/protoc --java_out=java/protocol/src/main/java/ gabriel.proto`

## Publishing Changes to PyPi

Update the version number in python/setup.py. Then follow [these instructions](https://packaging.python.org/tutorials/packaging-projects/#generating-distribution-archives).

## Publishing Changes to Maven Central

Follow [these instructions](https://github.com/cmusatyalab/gabriel-android-common/blob/master/README.md#publishing-changes-to-maven-central).
