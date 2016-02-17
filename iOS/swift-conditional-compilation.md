# Swift conditional compilation

Conditional compliation can be done with the following macros:

    #if <condition>

    #elseif <condition>

    #else

    #endif

Custom flags to use as the condition can be set in the Build Settings -> Swift Compiler - Custom Flags -> Other Swift Flags. Note that they must be prefixed with '-D'. I.e.:

	-D MY_FLAG