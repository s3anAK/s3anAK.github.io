# Lab Report #2
This report contains 3 parts: building a web server, addressing bugs, and what I learned.
## Building a Web Server
Here is the code for the Web Sever:
	
    
    import java.io.IOException;
    import java.net.URI;
    
    class Handler implements URLHandler {
        String returnString = "";
        boolean first = true;
        public String handleRequest(URI url) {
            if (url.getPath().equals("/add-message")) {
                String[] parameters = url.getQuery().split("=");
                if (parameters[0].equals("s") && first == false) {
                    returnString = returnString + "\n" + parameters[1];
                    return(returnString);
                } else if (parameters[0].equals("s") && first == true) {
                    returnString = parameters[1];
                    first = false;
                    return(returnString);
                }
                return returnString;
            }
                return "404 Not Found!";
            }
        }
    
    public class StringServer {
        public static void main(String[] args) throws IOException {
            if(args.length == 0){
                System.out.println("Missing port number! Try any number between 1024 to 49151");
                return;
            }
    
            int port = Integer.parseInt(args[0]);
    
            Server.start(port, new Handler());
        }
    }


### Example #1 for using `add-message`
![Screenshot 2023-01-26 145713](https://user-images.githubusercontent.com/56090826/214969456-5208427c-56e6-4968-98e3-a4ee40c9c46b.png)

 - The method called is `HandleRequest(URI  url)`.
 - The argument `url` for this method is `http://localhost:4000/add-message?s=Hello`
	 - The value of the field `returnString` when `handleRequest(URI url)` is called is an empty string.
		 - The value of this field is changed from an empty string to `Hello` during this method call.
	 - The value of the field `first` when `handleRequest(URI url)` is called is `true`
		 - The value of this field is changed from `true` to `false` during this method call.

### Example #2 for `add-message`
![stringServerAdd2](https://user-images.githubusercontent.com/56090826/214973838-ff92b705-7049-4b21-8bcc-0299a337e680.png)
 - The method called is `HandleRequest(URI url)`.
 - The argument `url` for this method is `http://localhost:4000/add-message?s=How are you`
	 - The value of the field `returnString` when `handleRequest(URI url)` is called is `Hello`.
		 - The value of this field is changed from `Hello` to `Hello \n How are you` during this method call.
	- The value of the field `first` when `handleRequest(URI url)` is called is `false`
		 - The value of this field is not changed during this method call because this is not the first call that the server is making.

## Addressing Bugs
The bug I am choosing to address is the one in the `reversed` method in `ArrayExamples.java` where it writes the new array from a blank array instead of reversing itself.
### Failure-Inducing Input:

    @Test
	public  void  testReversedfails() {
	int[] input1 = {1,2,3,4,5};
	assertArrayEquals(new  int[]{5,4,3,2,1}, ArrayExamples.reversed(input1));
	}
### Non Failure-Inducing Input

    @Test
	public  void  testReversed() {
	int[] input1 = { };
	assertArrayEquals(new  int[]{ }, ArrayExamples.reversed(input1));
	}
### The Symptom

![Screenshot 2023-01-26 221535](https://user-images.githubusercontent.com/56090826/215021706-4c6c59a6-ea4a-437e-a175-573e87c6233b.png)

### The Bug

**Before the fix:**

    static  int[] reversed(int[] arr) {
	int[] newArray = new  int[arr.length];
	for(int  i = 0; i < arr.length; i += 1) {
	arr[i] = newArray[arr.length - i - 1];
	}
	return  arr;
**After the fix:**

    static int[] reversed(int[] arr) {
	int[] newArray = new int[arr.length];
	for(int i = 0; i < arr.length; i += 1) {
	newArray[i] = arr[arr.length - i - 1];
	}
	return newArray;
	}
	
This fix addresses the issue because before, `arr` was being populated with values from `newArray` which was a blank integer array (just zeroes). I swapped the assignment statement in the for loop so the values from `arr` are being used to populate `newArray`. This makes it so that the values being put in to `newArray` are the reversed version of `arr`. I also changed the return statement to `return newArray` since newArray is the one that contains the reversed list.

## What I learned
I didn't know there was a framework and terminology for debugging code (symptoms, failure-inducing inputs, bugs, etc.). I always just tried to stare at my code until I figured out the problem, but with this framework and these terms in mind, I think I'll be much better at testing and debugging my code in the future. Learning Junit was also a big help in being able to test my code more efficiently.
