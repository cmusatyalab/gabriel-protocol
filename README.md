# Updating Protocol

Compile the proto for Python using version 3.10 of protoc or above. You can
download protoc for Linux from
[here](https://github.com/protocolbuffers/protobuf/releases/download/v3.12.3/protoc-3.12.3-linux-x86_64.zip).
You find links to download protoc for other platforms on
[this page](https://github.com/protocolbuffers/protobuf/releases). Just make
sure the archive you download begins with "protoc." After you download the
archive, extract it somewhere.

You can then compile `gabriel.proto` for Python by running the following line:
`/path/to/protoc --python_out=python/src/gabriel_protocol/ gabriel.proto`

Compile the proto for Java by opening the project in the `java` directory in
Android studio, clicking the `Gradle` button in the top right, and selecting
`java` > `Tasks` > `build` > `build`. Do not select any of the build tasks
specific to any of the modules (such as `protocol`).

## Publishing Changes to PyPi

Update the version number in python/setup.py. Then follow [these instructions](https://packaging.python.org/tutorials/packaging-projects/#generating-distribution-archives).

## Publishing Changes to Maven Central

Follow [these instructions](https://github.com/cmusatyalab/gabriel-android-common/blob/master/README.md#publishing-changes-to-maven-central).
