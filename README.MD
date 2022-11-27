<h1> GITEA Installation: </h1>

#git clone https://github.com/gauravkumar9130/gitea
#cd gitea
#kubectl create -f .

<h1> To verify: </h1>
#kubectl get pods -n gitea
#kubectl get svc -n gitea

<h1> Configure Gitea: </h1>
#kubectl get svc -n gitea
COPY LOAD BALANCER SERVICE IP AND OPEN WITH 3000 PORT NUMBER OR IF USING NODE PORT THEN USE ANY WORKER NODE IP WITH 3000 PORT NUMBER.

<h2> It will open configuration page: </h2> 
Database type: SQLite3
Site TITLE: Company Name
Server Base URL: (if using load balancer: http://<LOAD BALANCER IP>:3000) OR (if using node port: http://<ANY WOKER IP>:3000)
Git Base URL: (if using load balancer: http://<LOAD BALANCER IP>:3000) OR (if using node port: http://<ANY WOKER IP>:3000)

<h2> Server and Third Party Service Settings: </h2>
Disable self registration: Tick (IF YOU DON’T WANT USER TO CREATE ACCOUNT THEMSELVES ONLY ADMIN WILL BE ALLOWED)

<h2> Administrator Account Settings: BELOW USER WILL BECOME ADMINISTRATOR </h2>
	Administrator username: git-admin
	Password: admin
	Confirm password: admin
	email address: admin@admin.com

	Click on “Install Gitea”

<h1> Congratulations GITEA INSTALLED SUCCESFULLY :) </h1>


	
	 
<h1> FOR DEMO PURPOSE: </h1>
Register new user on home page with named user1

Create new repository with named demo-repo

IN DEVELOPER VM:
#mkdir project1
#vim index.html
hello web 
#git init
#git add .
#git commit -a -m “first commit”
#git remote add origin <REPOSITORY URL> 
	for example: #git remote add origin http://<LOAD BALANCER OR ANY WORKER IP>:3000/user1/demo-repo
#git push origin master
username: user1
password: userpassword

GO TO GITEA AND VERIFY


ADMIN USER CAN MANAGE ALL THE USERS AND ALL REPOSITORIES:
Logout from existing user and login with admin user we created at the time of initialization -> Click on user icon -> site administration -> here we will see all user and repositories information.
