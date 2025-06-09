# CLOUD-PROJECT-DOC
this is documentation for my submission for ICT171 Assignment 2

My name is Noah Schulz and my student id is 35673001

Click this link or copy and paste it into your search to see my website please: 
https://noahscv.com/


WEEK 1:
notes: this week was used for brain storming ideas and software that i could use to create my website. I experimented with wordpress and drupal on my instances but after testing them out, I discovered that I preffered to do what i was comfortable with and  just opted to use  HTML,CSS and Javascript in a file created with the sudo nano command that would be assigned as my homepage written out and compiled etc.

Development:

Login and create an account for amazon ec2
Go to amazon ec2 
navigate to instances press launch an instance

follow the prompts for creating an instance
settings selected:

Name: Noah's CV
Ubuntu selected
t2.micro free tier selected 
follow prompts for the rest
select create new security group with the settings

ssh port 22 - your ip
http port 80 - 0.0.0.0/0
https port 443 - 0.0.0.0/0

click launch instance

 connect to instance 
 
run commands :
sudo apt update
sudo apt install apache2 -y 
sudo systemct1 status apache2

go to http:// yourelasticip 
check if the apache default page is there 


exit and stop instance







WEEK 2:
notes: with my instance launched and decision made on how to make the website, I decided that my next course of action should be running python cert bot commands, getting an elastic ip and a custom domain for the instance, so that my next 2 weeks of development can be dedicated to creating the html page and designing it 

Development done:
log in to amazon ec2
navigate to elastic ips 
follow prompts, acquire and associate an elastic ip with the desired instance 

Go to  Amazon route 53 
navigate to hosted zones 

create hosted zone
enter name and follow prompts 
make sure the type is public hosted zone

navigate back to hosted zone 
in hosted zone click create record 
follow prompts enter the name you want leave most stuff as default except for value 
make sure the value is equal to the elastic ip associated with the instance being developed 

go to amazon ec2 start and connect to the instance being developed 

run commands:
sudo apt install certbot python3-certbot-apache -y

after installation run
sudo certbot --apache
enter the custom domain when prompted 
opt to redirect all http traffic to https

exit and stop instance






WEEK 3 and 4: 
note: So at the start of week three  I have not started coding however we have:
an instance with a domain and URL
https in the url
function webpage that can be access with the custom url
So I now deem this time appropriate to begin development and customise the website 

Commands ran throught the weeks:

sudo rm /var/html/index.html
sudo nano /var/html/index.html

over the time i developed this code here and put it into the index.html file



Below is the full HTML source code for my interactive online CV. You can use it, customize it, or integrate it into your own site.

https://github.com/nschulz883/CLOUD-PROJECT-DOC/blob/main/cv.html






THE FASTEST METHOD TO REPLICATE THIS WEBSITE:
IF everything works my project can be replicated verbatim within 3-5 hours
if you want to tailor it to yourself allow for an extra couple of hours ontop of the 3-5
from the instructions



FOLLOW THESE INSTRUCTIONS VERBATIM FOR SUCCESS:


Login and create an account for amazon ec2
Go to amazon ec2 
navigate to instances press launch an instance

follow the prompts and recommendations for creating an instance
settings selected:

Name: Noah's CV or your custom name
Ubuntu selected
t2.micro free tier selected 
follow prompts for the rest
select create new security group with the settings

under security group 
ssh port 22 - your ip
http port 80 - 0.0.0.0/0
https port 443 - 0.0.0.0/0

click launch instance

 connect to instance 
 
run commands :
sudo apt update
sudo apt install apache2 -y 
sudo systemct1 status apache2

go to http:// yourelasticip 
check if the apache default page is there 
close apache page 

navigate to elastic ips 
follow prompts, acquire and associate an elastic ip with the desired instance 

Go to  Amazon route 53 
navigate to hosted zones 

create hosted zone
enter name and follow prompts 
make sure the type is public hosted zone

navigate back to hosted zone 
in hosted zone click create record 
follow prompts enter the name you want leave most stuff as default except for value 
make sure the value is equal to the elastic ip associated with the instance being developed 

go to amazon ec2 start and connect to the instance being developed 

run commands:
sudo apt install certbot python3-certbot-apache -y

after installation run
sudo certbot --apache
enter the custom domain name from amazon route 53 when prompted 
opt to redirect all http traffic to https

sudo rm /var/html/index.html
sudo nano /var/html/index.html

copy the code verbatim write out, save and exit
or add your inforamtion customise first then write out or save


