The `tee' command copies standard input to standard output and also to any files given as arguments.  This is useful when you want not only to send some data down a pipe, but also to save a copy.

I wrote utility application to aid with debugging of applications started via command scripts on Windows XP used by Point2 Technologies, Inc. (Point2) where I am currently employed.

I found that most script output would scroll beyond the windows command line interface screen buffer and any error messages detected early in the execution of the script would be lost.  Coming from a Linux development environment where I used the tee command for this sort of debugging, I decided to write a version of the utility and donate the code to the company for my fellow Point2 developers to use.

Rather than keep the application internal to Point2, a mutual decision was made to open source the application and provide the code to the rest of the coding community.

The result is the wintee project.