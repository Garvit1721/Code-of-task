# DISCLAIMER
First of all I am not that much habitual of coding in python like I had IP in my class 12th but I didn't took it that seriously so I just know the basic of python programing but I am practicing to code in c++ and c and I have plan to learn python and data science in depth duriny my summer vaccation

# LEARNING 
**<ins>Making HTTP Request</ins>**

So for me making http request with the help of c++ and c was quite difficult but I am wanted to join KOSS so I have no other option left to shift over other programing language. So I searched over internet which will help me to make http request easier and from there I got to know that we can import a library named **requests** in python . 

**<ins>Created a Function</ins>**

Then I created a function which will be called after taking the input of the username and the repo name. So this function take two parameter username and repo name  

**<ins>Storing the Url</ins>** 

In the function I created a string which would be storing the url of the site. Here I used a f string which I used because I want to embed the username and repo name in that url

**url = f"https://api.github.com/repos/{username}/{repo}"**

**<ins>Creating the Headers</ins>**

Then I created a dictionary which would be storing the header which act as a additional piece of information for the server like **Accept** it used to specify the content that the user is expecting from the server.

**headers = {"Accept": "application/vnd.github.v3+json"}**

**<ins>Making the API request</ins>**

So I searched over the internet to know how to make the API request from there I got to know about **requests.get(url,headers)** . Here the url is basically that url to which i have to send the request and use of headers is already mentioned above . PS : the headers is key-value pair.

**response = requests.get(url,headers=headers)**

**<ins>After Making the Request</ins>** 

So After making the request there arise two cases :
1) Request is sent successfully : status_code == 200
2) Request is not sent successfully 
If the request is sent successfully then it will access the metadata
If the request is not sent successfully then it will print the error message

**<ins>Accessing the Meta data</ins>**

After making a succefull request I stored the data from the server in string in json format and for accessing the meta data I read commands from github api documentation . 
The commands are as follows : 


![Screenshot 2023-05-19 190517](https://github.com/Garvit1721/Code-of-task/assets/128980420/71664ac7-79a9-4211-94ce-70a9ff595fc3)

**<ins>ADDITIONAL LEARNING</ins>**

Apart from the learning of the requests library and some features of this library , I also learned about git and github as I don't know about it so I have to learn about them from scratch.

**<ins>CODE OUTPUT</ins>**

 I have you the github username of one of core team memeber of KOSS named Sahil Shubham to demonstrate the output of the code
  
![Screenshot 2023-05-21 222648](https://github.com/Garvit1721/Code-of-task/assets/128980420/84f02150-1f51-4753-bf34-aeb943d05cfc)           ![Screenshot 2023-05-21 222716](https://github.com/Garvit1721/Code-of-task/assets/128980420/24540c49-c8c6-4931-ad5e-e5248a308cf0)

  ![Screenshot 2023-05-21 222729](https://github.com/Garvit1721/Code-of-task/assets/128980420/b60ad30a-e41e-44d5-a20b-16fa062caf3b)



