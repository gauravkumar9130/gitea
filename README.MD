<h1> GITEA Installation: </h1>
#git clone https://github.com/gauravkumar9130/gitea <br />
#cd gitea <br />
#kubectl create -f . <br />

<h1> To verify: </h1>
#kubectl get pods -n gitea <br />
#kubectl get svc -n gitea <br />

<h1> Configure Gitea: </h1>
#kubectl get svc -n gitea <br />
<h2> COPY LOAD BALANCER SERVICE IP AND OPEN WITH 3000 PORT NUMBER OR IF USING NODE PORT THEN USE ANY WORKER NODE IP WITH 3000 PORT NUMBER. </h2>

<h2> It will open configuration page: </h2> 
Database type: SQLite3 <br />
Site TITLE: Company Name <br />
Server Base URL: (if using load balancer: http://<LOAD BALANCER IP>:3000) OR (if using node port: http://<ANY WOKER IP>:3000) <br />
Git Base URL: (if using load balancer: http://<LOAD BALANCER IP>:3000) OR (if using node port: http://<ANY WOKER IP>:3000) <br />

<h2> Server and Third Party Service Settings: </h2>
Disable self registration: Tick (IF YOU DON’T WANT USER TO CREATE ACCOUNT THEMSELVES ONLY ADMIN WILL BE ALLOWED) <br />

<h2> Administrator Account Settings: BELOW USER WILL BECOME ADMINISTRATOR </h2>
	Administrator username: git-admin <br />
	Password: admin <br />
	Confirm password: admin <br />
	email address: admin@admin.com <br />

	Click on “Install Gitea”

<h1> Congratulations GITEA INSTALLED SUCCESFULLY :) </h1>


	
	 
<h1> FOR DEMO PURPOSE: </h1>
Register new user on home page with named user1 <br />

Create new repository with named demo-repo <br />

IN DEVELOPER VM: <br />
#mkdir project1 <br />
#vim index.html <br />
hello web  <br />
#git init <br />
#git add . <br />
#git commit -a -m “first commit” <br />
#git remote add origin <REPOSITORY URL>  <br />
	for example: #git remote add origin http://<LOAD BALANCER OR ANY WORKER IP>:3000/user1/demo-repo <br />
#git push origin master <br />
username: user1 <br />
password: userpassword <br />

GO TO GITEA AND VERIFY <br />


ADMIN USER CAN MANAGE ALL THE USERS AND ALL REPOSITORIES:
Logout from existing user and login with admin user we created at the time of initialization -> Click on user icon -> site administration -> here we will see all user and repositories information.
