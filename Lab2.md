# Lab Report #2
This report contains 2 parts: building a web server and addressing bugs.
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
		 - The value of this field is changed from an empty string to `Hello` during this request.
	 - The value of the field `first` when `handleRequest(URI url)` is called is `true`
		 - The value of this field is changed from `true` to `false` during this method.
