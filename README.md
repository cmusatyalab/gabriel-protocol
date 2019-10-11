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

1. Update the VERSION_NAME parameter in `gradle.properties`. You can add
   `-SNAPSHOT` to the end of the version number to get a snapshot published
   instead.
2. Open the `Gradle` tab in the top right of Android studio.
3. Open `protocol/Tasks/upload`.
4. Run uploadArchives
5. Snapshots will be published to
   https://oss.sonatype.org/content/repositories/snapshots/edu/cmu/cs/gabriel/protocol/.
6. Relases should show up at https://oss.sonatype.org/#stagingRepositories.
   1. Publish a release by first clicking the `Close` button. Then click the
      `Release` button when it becomes available.
   2. Releases will be published to https://repo1.maven.org/maven2/edu/cmu/cs/gabriel/protocol/.
