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

<img width="473" alt="Screenshot 2023-10-21 at 7 37 22 PM" src="https://github.com/utkarshlohia/cse15l-lab-reports/assets/62682577/cee7c466-5ad2-47a0-8b37-1190fa7836b6">


- Methods called for `/add-message?s=Hello` : `public String handleRequest(URI url)`
- Arguments for the method: `URI url`. The value of `URI url` is https://localhost:4000/add-message?s=Hello
- Values of fields that change: `String str` was empty and it changes to "1. Hello\n". The value of `count` increases by 1.

<img width="546" alt="Screenshot 2023-10-21 at 7 37 31 PM" src="https://github.com/utkarshlohia/cse15l-lab-reports/assets/62682577/4d8d830a-1ee4-4ef3-818c-9c8ea9b3700c">

- Methods called for `/add-message?s=How are you` : `public String handleRequest(URI url)`
- Arguments for the method: `URI url`. The value of `URI url` is `https://localhost:4000/add-message?s=How are you`
- Values of fields that change: `String str` was empty and it changes to "1. Hello\n2. How are you\n". The value of `count` increases by 1. It becomes 2.


## Part 2: SSH Keys

<img width="512" alt="Screenshot 2023-11-05 at 12 46 03 PM" src="https://github.com/utkarshlohia/cse15l-lab-reports/assets/62682577/003589ce-8b67-45b6-adc7-2aaffb10a5e8">
(Changed)

<img width="1469" alt="Screenshot 2023-10-21 at 8 35 58 PM" src="https://github.com/utkarshlohia/cse15l-lab-reports/assets/62682577/579f9d34-65f8-4e01-9413-2262eebd77f4">

<img width="893" alt="Screenshot 2023-10-21 at 8 36 43 PM" src="https://github.com/utkarshlohia/cse15l-lab-reports/assets/62682577/dc4eecd8-e335-4959-90d5-00194b7fe454">


## Part 3:

Something I learnt in lab in weeks 2 and 3 was creating my own server and running it using a url. I also learnt how queries, paths and fragments make up a url. It was fascinating to see how I could see and make changes to other people's NumberServer and see the changes on my personal computer.
