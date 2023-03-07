Before starting to download kernel and implement system call we download following commands:-
* sudo apt-get install gcc
* sudo apt-get install libncurses5-dev
* sudo apt-get install bison
* sudo apt-get install flex
* sudo apt install make
* sudo apt-get install libssl-dev
* sudo apt-get install libelf-dev
* sudo add-apt-repository "deb http://archive.ubuntu.com/ubuntu $(lsb_release -sc) main
universe"
* sudo apt-get update
* sudo apt-get upgrade

I download a kernel and extract it in downloads folder
1 sc
![1](https://user-images.githubusercontent.com/127008532/223484813-677f85e7-0335-4b36-926e-b9416651d944.png)


I created a new folder named hello and went in the folder and open terminal
2 sc

Then i added a c code for system call “Hello World”
3 sc
4 sc

Now, we have to create a Makefile for our new folder to ensure that the code in the folder is
always compiled whenever the kernel is compiled.
5 sc
6 sc

Since we are creating a 64-bit system call according to our system we have to add the
system call entry into the syscall_64.tbl file which keeps the name of all the system calls in
our system.
7 sc
8 sc

Now we have to add the prototype of our system call in the system’s header file which is
located in the kernel folder
9 sc
10 sc

Now we add rollno in extraversion in kernels Makefile
11 sc

Now we have to create a config file for our kernel.
12 sc
13 sc
14 sc

Now we have to clean all of our existing object and executable file
15 sc
16 sc
Giving root access
-> by typing “sudo su” command in terminal
Now we have to install the kernel that we built
-> by typing “make modules_install install” in terminal

Now we check by using uname -r command
Before
19 sc
After
20 sc

Now checking syscall-hello
21 sc
