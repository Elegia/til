Sometimes it happens that an archive build launches and immediately quits. If that's the case check the device logs for the crash info. If the error is a missing or invalid dylib, proceed as follows:

* Verify that all frameworks are correctly linked and/or embedded.
* Verify that the frameworks belong to the correct targets.
* Clean the project. Quit and restart XCode. Try again.
* Remove and reinstall the provisioning profile. Restart XCode. Try again.
* If all else fails, create a new provisioning profile in the developer portal. Install in XCode. Restart XCode. Clean the project and try again.