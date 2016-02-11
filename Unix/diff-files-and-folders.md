# Diff files and folders

Sometimes you find yourself with two sets of the same files, but you're not sure how they differ from one another. To check which files differ, use the **diff** tool.

    diff --brief -Nr dir1/ dir2/


Drop the -N flag if you don't want new/deleted files marked as a difference.

Alternatively, you can calculate the checksums of the files in each directory and them compare the outputs via a diff tool.

    find . -type f -print0 | xargs -0 md5 > checksums.md5

The resulting list of files and their md5 checksum will be placed in the checksums.md5 file.