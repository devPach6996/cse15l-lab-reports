#Part 1
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
## When we pass `Hello` to `handleRequest`
![image](https://user-images.githubusercontent.com/122571122/215283776-d1c43fa9-0a18-47b8-8b2b-3ae229682c7c.png)

## When we pass `How are you` to `handleRequest`
![image](https://user-images.githubusercontent.com/122571122/215283808-166af5e0-36f7-4fa6-b3b2-d199d1c58a8e.png)

