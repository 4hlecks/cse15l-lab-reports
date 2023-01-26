# Servers and Bugs
## Servers 🖥️
This is my implementation of **StringServer**:
```java
import java.io.IOException;
import java.net.URI;
import java.util.ArrayList;

class Handler implements URLHandler {
    ArrayList<String> stringList = new ArrayList<>();
    int num = 0;

    public String handleRequest(URI url) {
        if (url.getPath().equals("/")) {
            return "Welcome to Alex's String Server!" + "\n"
                + "Type /add-message?s=<string> at the end of the URL!";
        }
        else {
            System.out.println("Path: " + url.getPath());
            if (url.getPath().contains("/add-message")) {
                // separate args in path by s=
                String[] parameters = url.getQuery().split("s=");
                // add the message separated by the s= to string list
                stringList.add(parameters[1]);
                // print everything in stringList separated a line at a time
                return String.join("\n", stringList);
            }
            // last case for any other path, 404 not found
            return "404 Not Found!";
        }
    }
}

class StringServer {
    public static void main(String[] args) throws IOException {
        if(args.length == 0){
            System.out.println("Missing port number! Try any number between 1024 to 49151");
            return;
        }

        int port = Integer.parseInt(args[0]);

        Server.start(port, new Handler());
    }
}
```
Examples of **StringServer** in usage:

<img width="406" alt="image" src="https://user-images.githubusercontent.com/122405896/214743789-46484627-3e80-4b1e-a797-c73f49985f0b.png">

In the screenshot above, the method being called is ```handleRequest(URI url)```.
The relevant argument to this method is ```localhost:4000/add-message?s=Hello!```, as this URL is used in the URI parameter for ```handleRequest(URI url)```.
Values in this class change due to this request. According to my implementation, because the path is ```/add-message?s=Hello!``` it grabs the string at index [1] separated by ```s=``` which is ```"Hello!"```. The server returns all the elements in **stringList** separated line by line, which only contains ```"Hello!"```. 

<img width="506" alt="image" src="https://user-images.githubusercontent.com/122405896/214744153-13d8639c-24e1-4010-8063-1ce6aca82dd6.png">

In the screenshot above, the method being called is also ```handleRequest(URI url)```.
The relevant argument to this method is ```localhost:4000/add-message?s=The%fifth%line.```, as this URL is used in the URI parameter for ```handleRequest(URI url)```.
As aforementioned, values in this class change due to this request. According to my implementation, because the path is ```/add-message?s=The%fifth%line.``` it grabs the string at index [1] separated by ```s=``` which is ```"The fifth line"``` *(Spaces are separated by %)*.
The server returns all the elements in **stringList** separated line by line, which contains ```"Hello!"```,```"Hello!"```,```"How are you doing?"```,```"This is a test message."```,```""The fifth line."```. 

## Bugs 🐛



## Discoveries 🧠


