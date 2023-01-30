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
* In the above codeblock, `handleRequest` method is called
* Since, it takes a string as a parameter, it can take any `int`, `URI`, and `Strings`
* No values change the specific requests because the value takes a string parameter
## When we pass `How are you` to `handleRequest`
* In the above codeblock, `handleRequest` method is called
* Since, it takes a string as a parameter, it can take any `int`, `URI`, and `Strings`
* Here, the value, which was passed in the earlier request stays there and the new request gets written below the previois one.
![image](https://user-images.githubusercontent.com/122571122/215283808-166af5e0-36f7-4fa6-b3b2-d199d1c58a8e.png)
#Part 2:-
## Failure inducing input
* In this test, I gave the input `5,6,7,8,9,10`
```
@Test
  public void testReversed() {
    int[] input = {5,6,7,8,9,10};
    assertArrayEquals(new int[]{10,9,8,7,6,5}, ArrayExamples.reversed(input));
  }
```
* The answer should be 10,9,8,7,6,5; but it failed
## Symptom
![image](https://user-images.githubusercontent.com/122571122/215357612-a23cd01d-7a79-46f3-8710-8073d0309a6f.png)
* In  this program, it never returned a new array, it just returned the array that we passed resulting in a wrong output.
* Now, here is an input that is not a failure inducing input
```@Test
  public void testReversed() {

    int[] input1 = {0};
    assertArrayEquals(new int[]{0}, ArrayExamples.reversed(input1));
    }
```
* We don't see any tests failed in Junit because in the for loop when i = 0, arr[i] and newArray[arr.length-i-1] have the same value, which is 0.
## Bug:-
* Before fixing the bug, the code looks like this.
* We can notice that the program is supposed to return a `newArray` but it return the old array `arr`, which is the reason we failed the test where we tried outputting 5 to 10 in reverse order 
* Another bug is that, in the for loop, `newArray` is supposed to be on the left side, since it is the array to which we assign values from `arr`, but in the given program the assgnment order of variables `newArray` and `arr` is changed.
   ```
     static int[] reversed(int[] arr) {
    int[] newArray = new int[arr.length];
    for(int i = 0; i < arr.length; i += 1) {
      arr[i] = newArray[arr.length - i - 1];
    }
    return arr;
  }
   ```
 * After fixing the bug, the code looks like this.
 ```
  static int[] reversed(int[] arr) {
    int[] newArray = new int[arr.length];
    for(int i = 0; i < arr.length; i += 1) {
      newArray[i] = arr[arr.length - i - 1];
    }
    return newArray;
  }
 ```
 * After fixing the bugs, I was able to solve the problem of not getting a new reversed array. Also, the order of assignment and the return value for the method was also changed, whcih helped me fix the program.
# Part 3:
* From week 2 and 3, I learned how professional programmers debug their programs and I also learned to write my own test, which sort of made my life very easier to     debug the code. Now, I don't have to run my program a thousand times to see what causes the error. 
