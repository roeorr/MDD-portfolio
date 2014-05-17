MDD1405-portfolio
=============
Deployment plan

I create a local repository on github and clone it to my local PC for my local development area.

You can then use a single tier server with apache installed for your staging/production server with only a single html page. 

You then need to install git on your staging/production server with the following commands:

	1.Install Git
		-sudo apt-get install git-core
	
	2.Configure Git
	    -git config --global user.name “NAME”
	    -git config --global user.email Your@Email.com
	
	3.Confirm Settings
	    -git config --list
	
	4.Create SSH Keys for Github Access
	
	    -cd ~/.ssh
	    -ssh-keygen -t rsa -C ”YourEmail@example.com”
	        This will ask if you want to customize the name, you don’t. Just press enter.
	   - Enter a passphrase
	   - Re-enter the passphrase
	
	5.Put the RSA key on file with github.com so this server is treated as a trusted machine.
	
	    -less ~/.ssh/id_rsa.pub
	        Copy ALL of the contents of this file to your clipboard.
	    -Add new SSH Key to your Github account under the Account Settings.

After git is installed you need to clone your git repo into /var/www/ (delete any index files that might already be in /var/www/)

After your repo is cloned you then need to enter that directory which is located at /var/www/project/ 

Use the command $ git pull and all your changes you made on your local staging server will be live on your server. If you are satisfied with your changes on your staging server then do the exact same command $ git pull on your production server and your changes will be live there.


