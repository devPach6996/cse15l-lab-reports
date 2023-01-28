Part 1
##  The code below creates a web server named `StringServer`, which keeps tracks of a single string arguments added by incoming requests.
```
import java.io.IOException;
import java.net.URI;
import java.io.*;
class Handler implements URLHandler {
    String message = "";
    public String handleRequest(URI url) {
        if (url.getPath().contains("/add-message")) {
            String[] parameters = url.getQuery().split("=");
            if (parameters[0].equals("s")) {
                message += parameters[1] + "\n";
                return message;
            }
        }
        return "404 Not Found!";
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
## This is how it looks like when we pass `Hello` to the url
![image](https://user-images.githubusercontent.com/122571122/215282469-ee86ffb0-9cbb-4b67-b89f-5121df505b36.png)
* The screen above uses `handleRequest` method, which takes `URI` as an argument
* Then, it looks for `/add-message`, if it finds that in the path, it will go into the if statement and will look for getQuerymethod, which will split the parameter
  using a `=` regex
* If the parameter is `s`, then the user can enter the string, which will store the value in `message`
* At the end, it will return the message.
* Since the value are stored as strings, it can take any arguments.
## Now when we pass another argument such as `How are you`, it will print both `Hello`, `How are you` in two lines
![image](https://user-images.githubusercontent.com/122571122/215282540-8249f7b4-e70b-422d-bb2e-06e4cf1fac01.png)
* The screen above uses `handleRequest` method, which takes `URI` as an argument
* Then, it looks for `/add-message`, if it finds that in the path, it will go into the if statement and will look for getQuerymethod, which will split the parameter
  using a `=` regex
* If the parameter is `s`, then the user can enter the string, which will store the value in `message`
* At the end, it will return the message.
* Since the value are stored as strings, it can take any arguments.
#Part 2
