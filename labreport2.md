## Part 1

Here is my code for *StringServer*. It keeps track of a single string that gets added tp by incoming requests:

import java.io.IOException;
import java.net.URI;

```
class Handler implements URLHandler {
String str="";

     public String handleRequest(URI url) {
        if (url.getPath().equals("/")) {
            return;
        } 
        else {
            System.out.println("Path: " + url.getPath());
            if (url.getPath().contains("add-message")) {
                String[] parameters = url.getQuery().split("=");
                
                    str=str.concat(parameters[1]+"\n");
                    return str;
                
            }
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
```



Example, using **/add-message>s=Hello** :

![image](https://user-images.githubusercontent.com/122485765/215639459-af4fb65d-efe3-4dec-9788-8b39774f45be.png)

using **/add-message>s=whatsup** :

![image](https://user-images.githubusercontent.com/122485765/215640246-6d393374-46a6-4648-badf-6a217f616ce2.png)


**Which methods in your code are called?**

The methods *StringServer* and then *handleRequest* are being called.

**What are the relevant arguments to those methods, and the values of any relevant fields of the class?**

**/add-message?s=Hello** is a relevant argument for screenshot 1 and **/add-message?s=whatsup** is a relevant argumemt for screenshot 2 - for handlerequest

**4000** is the argument for StringServer in both examples.

**How do the values of any relevant fields of the class change from this specific request? If no values got changed, explain why.**

Every time I pass a new argument, i.e. add a url request, the string argument gets added to the empty string that I created. Like in my examples, on passing "Hello" argument, hello gets added to string, followed by an empty line. Then, on calling "whatsup", it gets added to string followed by an empty line. So on and so forth.

According to my conditional statements, no change is made if the argument merely contains an "/" and the code exits the method.


## Part 2

The bug I chose:

ReverseInPlace

Failure inducing input as a JUnit Test:

```
@Test
  public void testReverseInPlace2digits() {
    int[] input1 = {1,3 };
    assertArrayEquals(new int[]{ 3,1}, ArrayExamples.reverseInPlace(input1));
  }
```
Test 1 for ReverseInPlace:
Input : {1,3}
Expects:{ 3,1}
Output:{3,3}

An input that does not induce a failure :

```
@Test
  public void testReverseInPlace2digits2() {
    int[] input1 = {1,1 };
    assertArrayEquals(new int[]{ 1,1}, ArrayExamples.reverseInPlace(input1));
  }
```
Test results:
Input : {1,1}
Expects:{ 1,1}
Output:{1,1}

Bugs Code:

```
// Changes the input array to be in reversed order
  static void reverseInPlace(int[] arr) {
    for(int i = 0; i < arr.length; i += 1) {
      arr[i] = arr[arr.length - i - 1];
    }
  }


  // Returns a *new* array with all the elements of the input array in reversed
  // order
  static int[] reversed(int[] arr) {
    int[] newArray = new int[arr.length];
    for(int i = 0; i < arr.length; i += 1) {
      arr[i]=newArray[arr.length-i-1];
      }
    return arr;
  }
```


Changed code:

```
// Changes the input array to be in reversed order
  static void reverseInPlace(int[] arr) {
    for(int i = 0; i < arr.length/2; i += 1) {
      int temp=arr[i];
      arr[i] = arr[arr.length - i - 1];
      arr[arr.length - i - 1]=temp;
    }
  }


  // Returns a *new* array with all the elements of the input array in reversed
  // order
  static int[] reversed(int[] arr) {
    int[] newArray = new int[arr.length];
    for(int i = 0; i < arr.length; i += 1) {
      newArray[arr.length - i - 1]=arr[i];
    }
    for(int i = 0; i < arr.length; i += 1) {
      arr[i]=newArray[i];}
    return arr;
  }
```

The problem - 

1. For reverseInPlace:

There was no creation of a variable to store element getting replaced. Instead an elment getting replaced disappears and there ends up being a repititon.

2. For reverse:

Just replacing and rewriting the elements will not work. You need to store the values and then copy into indices.

##Part 3

I did not know how to handle servers or work with URLs before lab in week 2


