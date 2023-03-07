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
![1](https://user-images.githubusercontent.com/127008532/223484813-677f85e7-0335-4b36-926e-b9416651d944.png)


I created a new folder named hello and went in the folder and open terminal
![2](https://user-images.githubusercontent.com/127008532/223485271-a5f1cb52-1142-4cf5-9f77-9d4e6264f28f.png)

Then i added a c code for system call “Hello World”
![3](https://user-images.githubusercontent.com/127008532/223485315-8dab3870-5b71-48fb-91eb-c8eb9f50b682.png)
![4](https://user-images.githubusercontent.com/127008532/223485352-1dc4174a-f6d5-4d4d-8b59-3989eafa39b3.png)

Now, we have to create a Makefile for our new folder to ensure that the code in the folder is
always compiled whenever the kernel is compiled.
![5](https://user-images.githubusercontent.com/127008532/223485385-d04fafc9-8519-4f42-b8fe-a868159d4273.png)
![6](https://user-images.githubusercontent.com/127008532/223485416-7f0c3dee-7363-4b44-8b1f-d0b12f58e927.png)

Since we are creating a 64-bit system call according to our system we have to add the
system call entry into the syscall_64.tbl file which keeps the name of all the system calls in
our system.
![7](https://user-images.githubusercontent.com/127008532/223485461-5618c114-2165-44ab-a349-1b622b622d18.png)
![8](https://user-images.githubusercontent.com/127008532/223485549-f3e845f4-1276-4e4a-af8e-9cd6009f092b.png)

Now we have to add the prototype of our system call in the system’s header file which is
located in the kernel folder
![9](https://user-images.githubusercontent.com/127008532/223485515-f841c951-e56a-44c2-9917-59480da61722.png)
![10](https://user-images.githubusercontent.com/127008532/223485581-d5537a1c-a9dd-4704-81bf-eec4c6d1dc4c.png)

Now we add rollno in extraversion in kernels Makefile
![11](https://user-images.githubusercontent.com/127008532/223485622-7e6597ff-4313-4259-90d2-a1761f55aef6.png)

Now we have to create a config file for our kernel.
![12](https://user-images.githubusercontent.com/127008532/223485686-57e25f54-5c93-4d2d-9d7f-1112370d9374.png)
![13](https://user-images.githubusercontent.com/127008532/223485750-baa741b5-b772-4af2-948f-88b4b4037fdb.png)
![14](https://user-images.githubusercontent.com/127008532/223485786-2f22714e-100d-4f74-abed-fded1e4c5b67.png)

Now we have to clean all of our existing object and executable file
![15](https://user-images.githubusercontent.com/127008532/223485827-7409a6c1-49e2-474b-9d33-0e2f5045dee1.png)
![16](https://user-images.githubusercontent.com/127008532/223485886-775a0b73-0701-4402-b272-03c4fa427439.png)


Giving root access
-> by typing “sudo su” command in terminal
Now we have to install the kernel that we built
-> by typing “make modules_install install” in terminal

Now we check by using uname -r command
Before
![19](https://user-images.githubusercontent.com/127008532/223485951-c3474a80-e9a4-4677-93d1-9495d9731577.png)
After
![20](https://user-images.githubusercontent.com/127008532/223485994-201930fc-b159-4e3d-88b6-3008e7b09617.png)

Now checking syscall-hello
![21](https://user-images.githubusercontent.com/127008532/223486042-810a14f1-1e11-42f0-be92-b3b58af26b00.png)
