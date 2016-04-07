# Symbolize crash log

From: http://stackoverflow.com/questions/25855389/how-to-symbolicate-crash-log-xcode

Requirements:

* The app IPA file
* The corresponding dSYM file
* The crash log

Step 1:

Move all the above files into the same folder.

Step 2:

Open the crash report in TextEdit, go to the Binary Images: section and copy the first address there (e.g. 0xd7000).

Step 3:

CD into the folder and run the following command:

	xcrun atos -o Foo.app/Foo -arch arm64 -l 0xd7000 0x0033f9bb


This will symbolicate the symbol at address 0x0033f9bb. This address comes from the first address column in the stack trace. 
Make sure to pick the correct value for the -arch option. This can be obtained from the first line in the Binary Images: section, or figured out from the Hardware model: in the crash report and the app's supported archs).

You can also copy the necessary stack trace addresses directly in a text file and perform the command on the text file.

The file should then look like this:

	0x00f12fb
	0x002726b7
	0x0026d415
	...

The command looks like:

	xcrun atos -o Foo.app/Foo -arch arm64 -l 0xd7000 -f addr.txt