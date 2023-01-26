# How to Log Into a Course-Specific Account on *ieng6*
## Installing Visual Studio Code 🖥️
To install **Visual Studio Code**, go to https://code.visualstudio.com

![image](https://user-images.githubusercontent.com/122405896/211925539-8cfa3f20-2e3b-4a88-baf8-8957fdbcc9be.png)

You will see three options to download from, each supporting their respective OS. Since I am on a **Windows PC**, I chose **Windows**.
Simply follow the installation steps and you should be good to go!

*Because I am doing this on a lab computer, **Visual Studio Code** was already installed, so I did not have to go through the installation steps.*

## Remotely Connecting 🔌
*Before getting started with this step, make sure you know your course-specific account information which can be found [here](https://sdacs.ucsd.edu/~icc/index.php).
Your course-specific account username should start with **cslwi23**.
If you don't know your password, learn how to reset it [here](https://docs.google.com/document/d/1hs7CyQeh-MdUfM9uv99i8tqfneos6Y8bDU0uhn1wqho/edit).*

*If you are on Windows, make sure you install [git](https://gitforwindows.org/). Follow the steps on this [post](https://stackoverflow.com/a/50527994) to make sure **git bash** is installed in Visual Studio Code.*

*Because I am doing this on a lab computer, **git** and **git bash** was already installed.*

![image](https://user-images.githubusercontent.com/122405896/211929076-1c3da88f-d659-493f-8926-5fd7cc82c96e.png)

Open Visual Studio Code and open the terminal, which can be done by doing *Ctrl + `*.

![image](https://user-images.githubusercontent.com/122405896/211930049-f35ad5eb-3410-4185-9f89-b899dc3e8f20.png)

Type in the above code, replacing *alg* with what letters are in your course-specific username. Then enter your password (*Even though letters may not show up when entering your password, it is still being inputted. So make sure you type your password correctly!*) and press enter.

![image](https://user-images.githubusercontent.com/122405896/211930294-d6abe4e2-a35d-4dc6-8b66-477d1346566c.png)

If it is your first time connecting, a question may pop up asking if you want to continue connecting, just enter yes and you will reach this screen.

**Congratulations! 🥳🎈** You are now remotely connected! To disconnect from the server, just do *Ctrl + D*.
## Trying Some Commands ⌨️
Let's try out some commands!

![image](https://user-images.githubusercontent.com/122405896/211931542-a07f69d2-af6d-4334-82bb-550fc97566d7.png)

**pwd** reveals the current directory.
**cd ..** goes back to the current directory, as shown above.

![image](https://user-images.githubusercontent.com/122405896/211931725-dac7b144-f5f2-449b-83f0-c38aed334e0c.png)

Here I tried accessing a directory involving another user's folder, however permission is denied!

![image](https://user-images.githubusercontent.com/122405896/211932687-e8b13306-71c5-403d-9c19-a9471e03fdd7.png)

Here I did **cat** on a text file on the lab computer, *not* the *remote server*.


