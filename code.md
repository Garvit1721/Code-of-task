import requests #this is a python library which is used to held http requests
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

    if response.status_code ==200 :
        #it checks whether the request is send succesfully or not 
        repo_data = response.json()
        #this line store the data from the server in the json format in the string repo_data

        #now accesing the metadata
        print("Repository Name:", repo_data["full_name"])
        print("Description:", repo_data["description"])
        print("Language:", repo_data["language"])
        print("Stars:", repo_data["stargazers_count"])
        print("Forks: ",repo_data["forks_count"])
        print("Watcher Count :",repo_data["subscribers_count"])
        if repo_data["private"] :
            print("Repository is private")
        else :
            print("Repository is public")
        if repo_data["license"]:
            print("License:", repo_data["license"]["name"])
        else:
            print("No license information found for this repository.")
    else :
        print("ERROR:",response.status_code)
        #if request is not successfull than it will show this error

#asking the user for input
username = input("Enter the GITHUB username : ")
repo = input("Enter the repository name: ")

#calling the function
get_repo_metadata(username,repo)


