```
$ bazelisk build --define=apple.experimental.tree_artifact_outputs=yes HelloWorld
...
INFO: Build completed successfully, 113 total actions

$ file bazel-bin/HelloWorld.app/HelloWorld 
bazel-bin/HelloWorld.app/HelloWorld: Mach-O 64-bit executable arm64

$ file bazel-bin/HelloWorld.app/Watch/HelloWorld-WatchApplication.app/HelloWorld-WatchApplication 
bazel-bin/HelloWorld.app/Watch/HelloWorld-WatchApplication.app/HelloWorld-WatchApplication: Mach-O 64-bit executable x86_64
```
