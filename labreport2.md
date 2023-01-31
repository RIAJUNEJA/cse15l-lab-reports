## Part 1

Here is my code for *StringServer*. It keeps track of a single string that gets added tp by incoming requests:

import java.io.IOException;
import java.net.URI;

class Handler implements URLHandler {
String str="";

     public String handleRequest(URI url) {
        if (url.getPath().equals("/")) {
            return str;
        } 
        else {
            System.out.println("Path: " + url.getPath());
            if (url.getPath().contains("add-message")) {
                String[] parameters = url.getQuery().split("=");
                
                    str=str+parameters[1]+"\n";
                    return str;
                
            }
            return "404 Not Found!";
        }
    }
}


class StingServer {
    public static void main(String[] args) throws IOException {
        if(args.length == 0){
            System.out.println("Missing port number! Try any number between 1024 to 49151");
            return;
        }

        int port = Integer.parseInt(args[0]);

        Server.start(port, new Handler());
    }
}

Example, using **/add-message>s=Hello** :

![image](https://user-images.githubusercontent.com/122485765/215639459-af4fb65d-efe3-4dec-9788-8b39774f45be.png)

using **/add-message>s=whatsup** :

![image](https://user-images.githubusercontent.com/122485765/215640246-6d393374-46a6-4648-badf-6a217f616ce2.png)


**Which methods in your code are called?**

The methods *StringServer* and then *handleRequest* are being called.

**What are the relevant arguments to those methods, and the values of any relevant fields of the class?**

**Server.start(port, new Handler());** is a relevant argument in **StringServer** 

**(URI url)** in **handleRequest**


How do the values of any relevant fields of the class change from this specific request? If no values got changed, explain why.


## Part 2

