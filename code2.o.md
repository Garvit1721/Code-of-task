import requests 
#this is a python library which is used to held http requests

def get_repo_metadata(username,repo) : 
    #creates a function which is taking username of github accound and repository name from the user as input

    url = f"https://api.github.com/repos/{username}/{repo}"
    #here i used the f string to embed the username and repo in the url which the function takes as a input from the user

    headers = {"Accept": "application/vnd.github.v3+json"}
    #here i created a header dictionary which will pass to the headers parameter of requests.get

    response = requests.get(url,headers=headers)
    #this line of the code is to make the api request
    #here get function of the library is called to retirive the data 
    #it take two parameters url which tell from which url it has to retriev the data 
    #and headers are additional pieces of information that can be included in the request to provide more details or instructions to the server
    #here i have used accept header which tells that that it has to accept information from the url in the form of json

    if response.status_code == 200 :
        #it checks whether the request is send succesfully or not 
        repo_data = response.json()
        #this line store the data from the server in the json format in the string repo_data

        #now accesing the metadata
        print("THE USERNAME ENTERED : ",username)
        print("REPOSITORY NAME ENTERED : ",repo)
        str = 'Y'
        while(str == 'Y' or str == 'y' ) :
         print("1) DESCRIPTION")
         print("2) LANGUAGE")
         print("3) STARS")
         print("4) FORKS")
         print("5) WATCHER COUNT")
         print("6) PRIVATE/PUBLIC")
         print("7) LICENSE")
         n = int(input("ENTER YOUR CHOICE : "))
         match n :
             case 1 : 
                 print("Repository Name:", repo_data["full_name"])
                 print("Description:", repo_data["description"])
             case 2 : 
                 print("Repository Name:", repo_data["full_name"])
                 print("Language:", repo_data["language"])
             case 3 :
                 print("Repository Name:", repo_data["full_name"])
                 print("Stars:", repo_data["stargazers_count"])
             case 4 : 
                 print("Repository Name:", repo_data["full_name"])
                 print("Forks: ",repo_data["forks_count"])
             case 5 :
                 print("Repository Name:", repo_data["full_name"])
                 print("Watcher Count :",repo_data["subscribers_count"])
             case 6 :
                 print("Repository Name:", repo_data["full_name"])
                 if repo_data["private"] :
                  print("Repository is private")
                 else :
                  print("Repository is public")
             case 7 : 
                 print("Repository Name:", repo_data["full_name"])
                 if repo_data["license"]:
                  print("License:", repo_data["license"]["name"])
                 else:
                  print("No license information found for this repository.")
         str = (input("press Y/y for getting more details else N/n : "))
    else :
        print("ERROR:",response.status_code)
        #if request is not successfull than it will show this error

#asking the user for input
username = input("Enter the GITHUB username : ")
repo = input("Enter the repository name: ")

#calling the function
get_repo_metadata(username,repo)
