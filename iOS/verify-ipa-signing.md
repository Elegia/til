# Verify IPA Signing

If you have issues with a signed IPA file, but you're not sure what's wrong, you can use the codesign tool to verify the file:

    $ codesign --verify -vvvv [nameofapp].app