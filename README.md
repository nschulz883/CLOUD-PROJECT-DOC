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


# My Online CV – HTML Source

Below is the full HTML source code for my interactive online CV. You can use it, customize it, or integrate it into your own site.

```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1" />
  <title>Online CV</title>
  <script src="https://cdnjs.cloudflare.com/ajax/libs/html2pdf.js/0.10.1/html2pdf.bundle.min.js"></script>
  <style>
    :root {
      --primary-color: #2c3e50;
      --secondary-color: #ecf0f1;
      --accent-color: #3498db;
      --font-stack: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
    }
    body {
      font-family: var(--font-stack);
      margin: 0;
      padding: 20px;
      background-color: var(--secondary-color);
      color: var(--primary-color);
      transition: background-color 0.3s, color 0.3s;
    }
    h1 {
      text-align: center;
      color: var(--accent-color);
      margin-bottom: 10px;
    }
    input[type="text"] {
      width: 100%;
      padding: 12px;
      margin: 20px auto;
      display: block;
      font-size: 16px;
      border: 1px solid #ccc;
      border-radius: 8px;
      box-shadow: 0 2px 4px rgba(0,0,0,0.05);
      transition: background-color 0.3s, color 0.3s;
    }
    button {
      display: block;
      margin: 10px auto;
      padding: 10px 20px;
      font-size: 16px;
      background-color: var(--accent-color);
      color: white;
      border: none;
      border-radius: 8px;
      cursor: pointer;
      transition: background-color 0.3s;
    }
    button:hover {
      background-color: #2980b9;
    }
    h2 {
      color: var(--accent-color);
      border-bottom: 2px solid var(--accent-color);
      padding-bottom: 5px;
      margin-top: 40px;
    }
    .cv-item {
      background: white;
      margin: 15px 0;
      padding: 15px;
      border-radius: 10px;
      box-shadow: 0 4px 8px rgba(0,0,0,0.05);
      transition: box-shadow 0.3s ease, background-color 0.3s;
    }
    .cv-item:hover {
      box-shadow: 0 6px 12px rgba(0,0,0,0.1);
    }
    .dropdown-header {
      cursor: pointer;
      background-color: var(--accent-color);
      color: white;
      padding: 12px;
      border-radius: 8px;
      font-weight: bold;
      transition: background-color 0.3s;
      user-select: none;
    }
    .dropdown-header:hover {
      background-color: #2980b9;
    }
    .dropdown-content {
      display: none;
      padding: 12px;
      border-top: 1px solid #ccc;
      margin-top: 10px;
      animation: fadeIn 0.3s ease-in-out;
    }
    .dropdown-content.active {
      display: block;
    }
    ul {
      padding-left: 20px;
    }
    @keyframes fadeIn {
      from { opacity: 0; }
      to { opacity: 1; }
    }
    body.dark-mode {
      background-color: #121212;
      color: #f0f0f0;
    }
    body.dark-mode input[type="text"] {
      background-color: #1e1e1e;
      color: #f0f0f0;
      border-color: #555;
      box-shadow: none;
    }
    body.dark-mode .cv-item {
      background-color: #1e1e1e;
      box-shadow: 0 4px 8px rgba(255 255 255 / 0.05);
    }
    body.dark-mode .cv-item:hover {
      box-shadow: 0 6px 12px rgba(255 255 255 / 0.1);
    }
    body.dark-mode .dropdown-header {
      background-color: #3a3a3a;
      color: #ddd;
    }
    body.dark-mode .dropdown-header:hover {
      background-color: #555;
    }
    body.dark-mode button {
      background-color: #555;
      color: #fff;
    }
    body.dark-mode button:hover {
      background-color: #777;
    }
  </style>
</head>
<body>
  <h1>My Online CV</h1>
  <input type="text" id="search" placeholder="Search CV entries..." />
  <button id="toggleAll">Toggle All Sections</button>
  <button id="toggleTheme">Toggle Dark/Light Mode</button>
  <button id="downloadPdf">Download CV as PDF</button>
  <h2>Work Experience</h2>
  <div class="cv-item" data-category="work">
    <div class="dropdown-header">Crew Member – Secret Harbour McDonald's</div>
    <div class="dropdown-content">
      <p><strong>Duration:</strong> August 2021 – June 2025</p>
      <ul>
        <li>Crew training</li>
        <li>Customer service</li>
        <li>Stock taking</li>
        <li>Restaurant cleaning</li>
      </ul>
    </div>
  </div>
  <div class="cv-item" data-category="work">
    <div class="dropdown-header">AI Prompt Writer – Data Annotation Tech</div>
    <div class="dropdown-content">
      <p><strong>Duration:</strong> February 2025 – May 2025</p>
      <ul>
        <li>Provide AI prompts and evaluate responses</li>
      </ul>
    </div>
  </div>
  <div class="cv-item" data-category="work">
    <div class="dropdown-header">Crew Member – Short Order Burger Baldivis</div>
    <div class="dropdown-content">
      <p><strong>Duration:</strong> May 2025 – Present</p>
      <ul>
        <li>Food preparation</li>
        <li>Stock taking</li>
        <li>Customer service</li>
      </ul>
    </div>
  </div>
  <h2>Volunteer Work</h2>
  <div class="cv-item" data-category="volunteer">
    <div class="dropdown-header">Weekend Volunteer – Salvation Army</div>
    <div class="dropdown-content">
      <p><strong>Duration:</strong> June 2023 – September 2023</p>
      <ul>
        <li>Customer service</li>
        <li>Shelf stocking</li>
      </ul>
    </div>
  </div>
  <div class="cv-item" data-category="volunteer">
    <div class="dropdown-header">Unpaid Intern – St Clair's Pharmacy</div>
    <div class="dropdown-content">
      <p><strong>Duration:</strong> February 2022 – March 2022</p>
      <ul>
        <li>Stock taking</li>
        <li>Customer service</li>
        <li>Cleaning</li>
      </ul>
    </div>
  </div>
  <h2>Certificates</h2>
  <div class="cv-item" data-category="certificates">
    <div class="dropdown-header">Introductory C Programming Specialization – Duke University</div>
    <div class="dropdown-content">
      <p><strong>Status:</strong> In Progress</p>
      <p><strong>Delivery:</strong> Online via Coursera</p>
    </div>
  </div>
  <div class="cv-item" data-category="certificates">
    <div class="dropdown-header">Python Basics – University of Michigan</div>
    <div class="dropdown-content">
      <p><strong>Status:</strong> In Progress</p>
      <p><strong>Delivery:</strong> Online via Coursera</p>
    </div>
  </div>
  <h2>Education</h2>
  <div class="cv-item" data-category="education">
    <div class="dropdown-header">WACE – Living Waters Lutheran College</div>
    <div class="dropdown-content">
      <p><strong>Duration:</strong> 2014 – 2024</p>
      <p><strong>Result:</strong> WACE Achieved, Graduated</p>
    </div>
  </div>
  <div class="cv-item" data-category="education">
    <div class="dropdown-header">Bachelor of Information Technology – Murdoch University</div>
    <div class="dropdown-content">
      <p><strong>Duration:</strong> February 2025 – November 2027 (Projected)</p>
      <p><strong>Majors:</strong> Artificial Intelligence & Machine Learning, Cybersecurity & Forensics</p>
    </div>
  </div>
  <div class="cv-item" data-category="education">
    <div class="dropdown-header">Master's Degree of Artificial Intelligence – Curtin University</div>
    <div class="dropdown-content">
      <p><strong>Duration:</strong> February 2028 – November 2028 (Projected)</p>
    </div>
  </div>
  <script>
    document.querySelectorAll('.dropdown-header').forEach(header => {
      header.addEventListener('click', () => {
        header.nextElementSibling.classList.toggle('active');
      });
    });
    document.getElementById('search').addEventListener('input', function () {
      const keyword = this.value.toLowerCase();
      document.querySelectorAll('.cv-item').forEach(item => {
        const text = item.innerText.toLowerCase();
        item.style.display = text.includes(keyword) ? '' : 'none';
      });
    });
    document.getElementById('toggleAll').addEventListener('click', () => {
      const allDropdowns = document.querySelectorAll('.dropdown-content');
      const allOpen = Array.from(allDropdowns).every(content => content.classList.contains('active'));
      allDropdowns.forEach(content => {
        content.classList.toggle('active', !allOpen);
      });
    });
    document.getElementById('toggleTheme').addEventListener('click', () => {
      document.body.classList.toggle('dark-mode');
    });
    document.getElementById('downloadPdf').addEventListener('click', () => {
      const allDropdowns = document.querySelectorAll('.dropdown-content');
      const originallyHidden = [];
      allDropdowns.forEach(content => {
        if (!content.classList.contains('active')) {
          content.classList.add('active');
          originallyHidden.push(content);
        }
      });
      setTimeout(() => {
        const element = document.body;
        const opt = {
          margin:       0.5,
          filename:     'CV.pdf',
          image:        { type: 'jpeg', quality: 0.98 },
          html2canvas:  { scale: 2, useCORS: true },
          jsPDF:        { unit: 'in', format: 'letter', orientation: 'portrait' }
        };
        html2pdf().set(opt).from(element).save().then(() => {
          originallyHidden.forEach(content => content.classList.remove('active'));
        });
      }, 300);
    });
  </script>
</body>
</html>


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


