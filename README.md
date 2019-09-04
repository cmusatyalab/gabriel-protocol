# Updating Protocol
When cloning this repository for the first time, you must run
`git submodule update --init --recursive` to check out all of the gabriel-common
repositories. These repositories contain files generated from `gabriel.proto`,
and these files must be updated any time `gabriel.proto` is modified. When
making future changes to the protocol, update this repository and all of its
submodules with the command `git pull --recurse-submodules` before making any
changes.

You should use version 3.0 of the protobuf compiler. You can find instructions
to download a binary of this version of the compiler
[here](https://github.com/tensorflow/models/blob/master/research/object_detection/g3doc/installation.md#manual-protobuf-compiler-installation-and-usage).
The compiler takes a while to build, so I recommend downloading a binary instead
of compiling it yourself.

You can then compile `gabriel.proto` by running the following lines:
1. `/path/to/protoc --python_out=gabriel-server-common/ gabriel.proto`
2. `/path/to/protoc --java_out=../client/legacy-android-client/app/src/main/java/ update.proto`

Commit and push changes to this repository and its submodules by running
`./commit_push_changes`

# Other Potentially Helpful Information

You can check the status of submodules with the command `git submodule status`.

Note that Scarlet does not use protobuf lite. Therefore, we use the standard
protobuf compiler for the Android client.
