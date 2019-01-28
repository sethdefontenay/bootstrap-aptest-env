# bootstrap-aptest-env
Easy way:
- Pull this repo to get started
- Install [Virtualbox](https://www.virtualbox.org/wiki/Downloads)
- Install [Vagrant](https://www.vagrantup.com/downloads.html)
- Run the `vagrant up` from this repos directory (I use git bash, if cmd doesn't work, you could try it)
- Let it do its thing (could be 15-20mins)(A window will appear, Don't login until the vagrant script is finished)
- Login using these details: 
	- Username: `vagrant`
	- Password: `vagrant`
- `Ctrl+Alt+T` to open a terminal
- Execute the following commands:
  - `cd apbackendtest`
  - `source venv/bin/activate`
  
Now you can execute commands against the project
- `inv --list` will show you a list of all commands
The main points will be linting, testing and bringing up the service
  - `inv lint`
  - `inv test`
  - `inv up`
Once you `inv up` you will build a new docker container
The service is most easily accessed using Postman
- Open postman
- Create a new GET request `localhost:5000/course/`
- Add a Header 
  - Key: `Authorization`
  - Value: `dev`
  
 - Send a request
 - POST new items to the api like this:
  	- POST `localhost:5000/course/`
  - Enter the body tab in postman
  	- Select `raw` as the encoding type
  	- Paste in something like this: `{
		"course_title": "test course title the first",
		"course_description": "test course description",
		"course_type": "public"
		}`
	- Post a few items and check the topfive endpoint:
		- GET `localhost:5000/course/topfive/`
