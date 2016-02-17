# Check framework architectures

If you want to check which architectures are supported by an iOS framework, use the **lipo** tool and apply it on the binary file within the framework bundle.

    $ lipo -info myframework.framework/myframework

The lipo tool also works on .a static library files. In fact, the binary file within a framework bundle is a .a file.

Example:

    $ lipo -info M13ProgressSuite.framework/M13ProgressSuite
    Architectures in the fat file: M13ProgressSuite.framework/M13ProgressSuite are: i386 x86_64 armv7 arm64