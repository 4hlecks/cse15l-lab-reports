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

The bug I will be focusing on is the ```reverseInPlace(int[] arr)``` method in **ArrayExamples.java**.

**Successful Input**:
```java
@Test 
    public void testReverseInPlaceSingle() {
        int[] input = { 3 };
        ArrayExamples.reverseInPlace(input);
        assertArrayEquals(new int[]{ 3 }, input);
        }
```

**Failure-Inducing Input**:
```java
@Test
    public void testReverseInPlaceMultiple() {
        int[] input = { 1 , 2 , 3 , 4 , 5 };
        ArrayExamples.reverseInPlace(input);
        assertArrayEquals(new int[]{ 5 , 4 , 3 , 2 , 1 }, input);
        }
```
**JUnit Tests**:

<img width="809" alt="image" src="https://user-images.githubusercontent.com/122405896/214754176-3c9d4242-d508-477b-a992-f4a214d42592.png">

In short, the first test would work because it is simply an array of one element. It would iterate through the for loop once setting the array element at index [0] to the array element at index [0].

The second test fails as it does not output the desired output: a reversal of the array, which is a symptom of the method. The expected output is the array ```{5,4,3,2,1}```, but instead we get ```{5,4,3,4,5}```.

**Original Code**:
```java
static void reverseInPlace(int[] arr)   {
    for(int i = 0; i < arr.length; i += 1)  {
        arr[i] = arr[arr.length - i - 1];
    }
}
```
**Revised Code**:
```java
static void reverseInPlace(int[] arr)   {
    int[] temp = new int[arr.length];
    for(int i = 0; i < arr.length; i += 1)  {
        temp[i] = arr[arr.length - i - 1];
    }
    
    for (int i = 0; i < arr.length; i++)    {
        arr[i] = temp[i];
    }
}
```

By adding a **temp array**, the original elements in the **input array** are no longer lost, as opposed to the original code where the original elements were being overwritten. Then you deep copy the elements from the **temp array** back to the **input array**, thus giving a reversal of the input array.

## Discoveries 🧠

These past two labs have definitely been interesting and I have enjoyed what we have been learning! When I was in fourth grade, I was really into the game, *Minecraft*. Going as far as trying to make my own server for my friends and I to play on. There were a ton of steps and words that I was clueless on, that I feel educated on now.
This includes the difference between a **localhost** and a **remote** server. When trying to start a server locally, only you have access to it via the localhost URL. However, when starting a remote server, you and other people are able to access it. During the lab when we made a remote server and I was able to access my partner's URL, I was astonished. When I tried making my own local server in fourth grade, I was confused as to why none of my friends were able to join it, as opposed to starting a server using a remote website, where they were able to join it.
