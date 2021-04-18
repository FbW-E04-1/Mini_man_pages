Linux which command is used to identify the location of a given executable that is executed when you type the executable name (command) in the terminal prompt. The command searches for the executable specified as an argument in the directories listed in the PATH environment variable.

which [OPTIONS] FILE_NAME...

For example, to find the full path of the ping command , you would type the following:

which ping
Copy
The output will be something like this:

/bin/ping
Copy
You can also provide more than one arguments to the which command:

which netcat uptime
Copy
The output will include full paths to both netcat and uptime executables:

/bin/netcat
/usr/bin/uptime
Copy
The search is done from left to right, and if more than one matches are found in the directories listed in the PATH path variable, which will print only the first one. To print all matches, use the -a option:

which -a touch
Copy
The output will show two full paths to the touch command :

/usr/bin/touch
/bin/touch
Copy
Usually one of the executables is only a symlink to the other one, but in some cases, you may have two versions of the same command installed in different locations or totally different commands using the same name.
