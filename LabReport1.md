# Lab Report 1


For my first use of ls which contained no arguments, lecture1 was the only item in the /home directory so it was only printed out. The working directory would be /home. The reason I had gotten this output is because ls calls for a list of the current directory contents. Since there are no arguments, this means all shell arguments are printed so it will print out just the lecture1 directory instead of providing a current directory. This output is expected. 

![Image](ls1.png)

For my second use of ls which was used with a path to a directory as an argument, the working directory would still be /home. The reason I got this output is because the argument was lecture1, so the program printed out the lecture1 contents. This output is as expected. 

![Image](ls2.png)

For my third use of ls which was used with a path to a file as an argument, the working directory would now be /home/lecture1. For my output I had received an error as there was no file in the directory. This makes sense as I had first printed the contents inside of lecture1, then I had printed the list of contents inside of the messages folder. When I tried to list the contents of the en-us.txt file though, it would come out as an error as there would be no files inside of the en-us.txt file. This output was an expected error output. 

![Image](ls3.5.png)

For my first use of cd which contained no arguments, the working directory was switched to /home. Due to there being no argument, the working directory was changed to /home, despite the working directory already being at /home. If the workign directory had been something like /home/lecture1/messages then the working directory have been changed back to /home if no arguments had been given. This output and directory change is as expected as there was no error. 

![Image](cd1.png)

For my second use of cd which was used with a path to a directory as an argument, the working directory would be under /home/lecture1. For my output, cd changed the directory of the home directory to the lecture1 folder. If ls is printed then this would list all the contents of the lecture1 folder on the screen. This output is expected. 

![Image](cd2.png)

For my third use of cd which was used with a path to a file as an argument, the working directory would be under /home/lecture1/messages. There was a notice printed out that "en-us.txt" was not a directory, so the directory wouldn't be able to change to that input. This would show an error because nothing had happened, although when the error occurred Ed threw that message. This output was expected as en-us.txt is not in the directory since it is a file. Cd is only looking for directories as arguments. 

![Image](cd3.png)

For my first use of cat which contained no arguments, the working directory is /home. For my output, cat displays the contents of any file and since there was no argument given, nothing will be printed out. The terminal is waiting for an input, but since no error message is thrown, so this would not be an error.

![Image](cat1.png)

For my second use of cat which was used with a path to a directory as an argument, the working directory would be under /home. It would also produce an error and this is because the question is calling for a path to a directory, but cat only prints the contents of a file. This output is expected as it cannot work on a directory. 

![Image](cat2.png)

For my third use of cat which was used with a path to a file as an argument, the working directory would be under /home/lecture1/messages. It would produce the contents within the "en-us.txt" file which is 'Hello World!', this is because cat can only print the contents of a file. There was no error. 

![Image](cat3.png)
