#git clone https://github.com/gauravkumar9130/gitea
#cd gitea
#kubectl create -f .

To verify:
#kubectl get pods -n gitea
#kubectl get svc -n gitea

Configure Gitea:
#kubectl get svc -n gitea
COPY LOAD BALANCER SERVICE IP AND OPEN WITH 3000 PORT NUMBER OR IF USING NODE PORT THEN USE ANY WORKER NODE IP WITH 3000 PORT NUMBER.

It will open configuration page:
Database type: SQLite3
Site TITLE: Company Name
Git Base URL: (if using load balancer: http://<LOAD BALANCER IP>:3000) OR (if using node port: http://<ANY WOKER IP>:3000)

Administrator Account Settings: BELOW USER WILL BECOME ADMINISTRATOR
	Administrator username: git-admin
	Password: admin
	Confirm password: admin
	email address: admin@admin.com

	Click on “Install Gitea”

Congratulations :)


FOR DEMO PURPOSE:
Register new user on home page with named user1

Create new repository with named demo-repo

IN DEVELOPER VM:
#mkdir project1
#vim
<h1> hello web </h1>
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
