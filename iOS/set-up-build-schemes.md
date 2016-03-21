# Set up build schemes

Sometimes it happens that the same project may have multiple build targets, each with a different webservice or flag. Rather than create a
new target, this can be solved with the use of schemes. Via the Swift Other Swift Flags settings you can set a flag to indicate which properties the build must use 

I.e. in case the project has two possible builds (one for sales, another for distributors), each with a different webservice:

Create three schemes:

* PROJECT_NAME
* PROJECT_NAME_A Sales
* PROJECT_NAME_B Distribution

PROJECT_NAME_A: This is the standard debug build used for development. It has the flag -D DEBUG set.
PROJECT_NAME_B: This is build option 1. It could for example have the flag -D SALES set.
PROJECT_NAME_C: This is build option 2. It could have the flag -D DISTRIBUTOR set.

The flags can be set in the target's (NOT the project's) build settings -> Swift Compiler - Custom Flags -> Other Swift Flags

Note that the first scheme, PROJECT_NAME, should never be archived into a build. This can be disabled by editing the scheme and unchecking
the 'Archive' checkbox in the Build tab.
