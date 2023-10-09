For my first use of ls which contained no arguments, the working directory would be ~ or /home. The reason I had gotten this output is because ls calls for a list of the current directory contents. Since there are no arguments, this means all shell arguments are printed so it will print out just the lecture1 directory instead of providing a current directory. This output is expected. 

![Image](ls1.png)

For my second use of ls which was used with a path to a directory as an argument, the working directory would still be /home. The reason I got this output is because it printed the contents of the current directory list inside of the lecture1 directory. This output is as expected. 

![Image](ls2.png)

For my third use of ls which was used with a path to a file as an argument, the working directory would now be /home/lecture1. For my output I had received an error as there was no file in the directory. This makes sense as I had first printed the contents inside of lecture1, then I had printed the list of contents inside of the messages folder. When I tried to list the contents of the en-us.txt file though, it would come out as an error as there would be no files inside of the en-us.txt file. This output was an expected error output. 

![Image](ls3.5.png)

For my first use of cd which contained no arguments, the working directory would be /home. For my output, cd is supposed to output whatever the current directory is instead of changing the directory like it is supposed to do. 
![Image](cd1.png)
![Image](cd2.png)
![Image](cd3.png)
![Image](cat1.png)
![Image](cat2.png)
![Image](cat3.png)
