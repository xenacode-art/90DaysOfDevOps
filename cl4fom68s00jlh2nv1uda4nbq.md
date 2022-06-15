## 90DaysOfDevops Day 8.

> Before we get into some of the fundamentals of Go we should get Go installed on our workstation and do what every "learning programming 101" module teaches us which is to create the Hello World app. As this one is going to be walking through the steps to get Go installed on your workstation we are going to attempt to document the process in pictures so people can easily follow along.
> 
> First of all, let's head on over to [Go website](go.dev/dl) and you will be greeted with some available options for downloads.
> 
> If we made it this far you probably know which workstation operating system you are running so select the appropriate download and then we can get installing.

![Screenshot 2022-06-15 at 15-04-25 Downloads - The Go Programming Language.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1655301906351/FRG5mh7M4.png align="left")

Also note if you do have an older version of Go installed you will have to remove this before installing, Windows has this built into the installer and will remove and install as one.

Once finished you should now open a command prompt/terminal and we want to check that we have Go installed. If you do not get the output that we see below then Go is not installed and you will need to retrace your steps.


![image.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1655302008608/6fjUqXmIH.png align="left")

- Next up we want to check our environment for Go. This is always good to check to make sure your working directories are configured correctly, as you can see below we need to make sure you have the following directory on your system.


![image.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1655302147627/DrqNyxIJY.png align="left")

Did you check? Are you following along? You will probably get something like the below if you try and navigate there.


![image.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1655302311441/n9eqd81xk.png align="left")

Ok, let's create that directory for ease I am going to use the "mkdir "command in  powershell terminal . We also need to create 3 folders within the Go folder as you will see also below.

![image.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1655302406948/Is4JTrdvO.png align="left")

Now we have Go installed and we have our Go working directory ready for action. We now need an integrated development environment (IDE) Now there are many out there available that you can use but the most common and the one I use is Visual Studio Code or Code. You can learn more about IDEs here %[https://www.youtube.com/watch?v=vUn5akOlFXQ].

If you have not downloaded and installed VSCode already on your workstation then you can do so by heading here. As you can see below you have your different OS options.


![image.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1655302479051/CkngbL3fB.png align="left")

Much the same as with the Go installation we are going to download and install and keep the defaults. Once complete you can open VSCode and you can select Open File and navigate to our Go directory that we created above.


![image.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1655302514268/Q2NezrNPt.png align="left")

You may get a popup about trust, read it if you want and then hit Yes, trust the authors. (I am not responsible later on though if you start opening things you don't trust!)

Now you should see the three folders we also created earlier as well and what we want to do now is right click the src folder and create a new folder called Hello

Pretty easy stuff I would say up till this point? Now we are going to create our first Go Program with no understanding about anything we put in this next phase.

- Next create a file called main.go in your Hello folder. As soon as you hit enter on the main.go you will be asked if you want to install the Go extension and also packages you can also check that empty pkg file that we made a few steps back and notice that we should have some new packages in there now?


![image.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1655302583272/RZYpofUGe.png align="left")
- Now let's get this Hello World app going, copy for the following code into your new main.go file and save that.

                           package main

                       import "fmt"

                   func main() {
                   fmt.Println("Hello #90DaysOfDevOps")
                        }

- Back in the terminal and in our Hello folder we can now check that all is working. Using the command below we can check to see if our generic learning program is working.

                      go run main.go

- It doesn't end there though, what if we now want to take our program and run it on other Windows machines? We can do that by building our binary using the following command


![image.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1655302709419/g5iEgpp4M.png align="left")

## Resources 

- https://www.youtube.com/watch?v=yyUHQIec83I

- https://www.youtube.com/watch?v=YS4e4q9oBaU&t=1025s

