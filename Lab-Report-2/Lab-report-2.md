# Lab Report 2 
## Part 1: StringServer

Code for StringServer.java

```
import java.io.IOException;
import java.net.URI;

class Handler implements URLHandler {
    // The one bit of state on the server: a number that will be manipulated by
    // various requests.
    String str = "";
    int count = 1;

    public String handleRequest(URI url) {
        
        if (url.getPath().equals("/")) {
            if (str.isEmpty()){
                return "String is empty.No message added yet.";
            }
            else{
                return str;
            }
        }
        if (url.getPath().contains("/add-message")) {
            String[] parameters = url.getQuery().split("=");
            if (parameters[0].equals("s")) {
                str+=count + ". "+parameters[1]+"\n";
                count = count+1;
                return str;
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

![First Time using add](https://github.com/utkarshlohia/cse15l-lab-reports/blob/main/Lab-Report-2/Screenshot%202023-10-21%20at%207.37.22%20PM.png)

- Methods called for `/add-message?s=Hello` : `public String handleRequest(URI url)`
- Arguments for the method: `URI url`. The value of `URI url` is https://localhost:4000/add-message?s=Hello
- Values of fields that change: `String str` was empty and it changes to "1. Hello\n". The value of `count` increases by 1.

## Part 2: SSH Keys

![Path to private ssh key](https://github.com/utkarshlohia/cse15l-lab-reports/blob/main/Lab-Report-2/Screenshot%202023-10-21%20at%208.24.02%20PM.png)

![Path to public key](https://github.com/utkarshlohia/cse15l-lab-reports/blob/main/Lab-Report-2/Screenshot%202023-10-21%20at%208.35.58%20PM.png)

![ssh without password](https://github.com/utkarshlohia/cse15l-lab-reports/blob/main/Lab-Report-2/Screenshot%202023-10-21%20at%208.36.43%20PM.png)

## Part 3:

Something I learnt in lab in weeks 2 and 3 was creating my own server and running it using a url. I also learnt how queries, paths and fragments make up a url. It was fascinating to see how I could see and make changes to other people's NumberServer and see the changes on my personal computer.
