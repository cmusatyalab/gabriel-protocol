When cloning this repository for the first time, you must run
`git submodule update --init` to check out all of the gabriel-common
repositories. These repositories contain files generated from `gabriel.proto`,
and these files must be updated any time `gabriel.proto` is modified.

You should use version 3.0 of the protobuf compiler. You can find instructions
to download a binary of this version of the compiler
[here](https://github.com/tensorflow/models/blob/master/research/object_detection/g3doc/installation.md#manual-protobuf-compiler-installation-and-usage).
The compiler takes a while to build, so I recommend downloading a binary instead
of compiling it yourself.

You can then compile `gabriel.proto` by running the following lines:
1. `/path/to/protoc --python_out=gabriel-server-common/ gabriel.proto`
2. `/path/to/protoc --java_out=../client/legacy-android-client/app/src/main/java/ update.proto`

You must commit changes to submodules with the command
`git push --recurse-submodules=check`. You can check the status of submodules
with the command `git submodule status`.

Note that Scarlet does not use protobuf lite. Therefore, we use the standard
protobuf compiler for the Android client.
