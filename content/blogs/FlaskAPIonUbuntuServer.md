+++
title = 'Deploying Python Flask API on Ubuntu Server: A Step-by-Step Guide'
date = 2024-01-16T10:57:45+05:30
draft = false
tags = ['Python', 'Flask', 'Server', 'Deployement', 'Ubuntu']
author = "Praveen Maurya"
+++

## Introduction

![](/images/FlaskAPI/flask.api.png)

Python's Flask framework is a popular choice for building web applications and APIs due to its simplicity and flexibility.In this blog, I'll guide you through the process of deploying a Python Flask API on an ubuntu server. Your server provider may be different but the process of API deployment will be same in 90% cases. By the end of this blog, you'll have a fully functional Flask API accessible over the internet.

### Prerequisites

Before we begin, make sure you have the following:

 - An Ubuntu server(you can use a virtual machine, a cloud server or a physical machine).
 - SSH access to your server.
 - Python installed on your server.
 - Basic knowledge of Python and Flask.

### Step-1: Update and Upgrade the System

Ensure your system is up-to-date by running the flowwing commands:

```
 sudo apt update
 sudo apt upgarde
```

Make sure to create a directory before creating the virtual environment. When you will login on the server the default struture will be empty. make a directory using the following commands:

```
 mkdir zero(projectName)
```

Now  all the action ralated to Project **zero** will be performend inside if the zero directory.

Note: zero is the project name.

### Step-2: Install Required Packages

Install necessary packages for running Flask and serving your API:

```
 sudo apt install python3-pip
 sudo apt install python3-virtualenv
 virtualenv zero_venv
 source zero_venv/bin/activate
```

![](/images/FlaskAPI/FlaskAPI_venv.png)

zero_venv:
 - zero_venv is the name of our virtaul environment.
source zero_venv/bin/activate:
 - This command is use to enable or activate our virtual environment for deactivating you can use command deactivate.

Now install the Flask inside the virtual environment using the following commands:

```
 pip install Flask
```

![](/images/FlaskAPI/Flask.png)

### Step-3: Port Configuration on server

On different service provider the configuration of port differs, but it will be inside the "Security Group>Edit inbound rules>Add Rule" something like this kind of configuration on all the services provider. I'm using oracle services for the server.

**Port Configuration on oracle server**

For enabling the Port on the oracle we have to use the following commands:

```
 sudo iptables -I INPUT 6 -m state --state NEW -p tcp --dport 8000 -j ACCEPT
 sudo iptables -I INPUT 6 -m state --state NEW -p udp --dport 8000 -j ACCEPT
 sudo netfilter-persistent save
```  

**Port Configuration UFW**

Step-1: Chacek the IPv6 If No the change it to yes

```
 sudo nano /etc/default/ufw
```

![](/images/FlaskAPI/ufw.png)

Step-2: Setting up default Policies

```
 sudo ufw default deny incoming
 sudo ufw default allow outgoing
```

Step-3 Enable the UFW

```
 sudo ufw enable
```

Step-4 Allowing ssh coonection and Port

```
 sudo ufw allow ssh
 or
 sudo ufw allow 22
 or
 sudo ufw allow 2222
```

Allowing the Ports

```
 sudo ufw allow 8000/tcp
 sudo ufw allow 8000/udp
 or 
 sudo ufw allow 8000:8007/tcp
 sudo ufw allow 8000:8007/udp
```

### Step-4: Create Flask App

Create a simple Flask app (e.g., app.py):
 - Create it at same level of virtual environment.

![](/images/FlaskAPI/app.py.png)

### Step-5: Gunicorn setup and automation

Installing Gunicorn(a production-ready WSGI server):

```
 pip install gunicorn
```

Run Flask App Locally - Test your Flask app locally to ensure it works.

```
 gunicorn -w 4 -b 0.0.0.0:8000 app:app
```

Visit http://your_server_ip:8000 in your browser to see the "Flask API Live!" message.
see the below screenshot.

![](/images/FlaskAPI/app.py.png)

**Configure Gunicorn Services**

Ensuring the continuous availability of our Flask API even after exiting the virtual environment is essential for a seamless development and deployment experience. To achieve this, I'll implement an automatic start mechanism for Gunicorn every time the virtual environment is activated. This enhancement ensures that the Flask API remains live, persistent, and ready to serve requests, eliminating the need for manual intervention during updates or the creation of new APIs. By integrating this auto-start feature into the virtual environment activation process, we streamline the development workflow and maintain a consistent and reliable connection to our Flask application.

**Create a Gunicorn systemd service file**

```
 sudo touch /etc/systemd/system/zero.service
 sudo nano /etc/systemd/system/zero.service
```

Now update the file with the following code:

```
 [Unit]
 Description=Gunicorn instance to serve your Flask API
 After=network.target
 [Service]
 User=your_user
 Group=your_user_group
 WorkingDirectory=/path/to/your_flask_project
 Environment="PATH=/path/to/venv/bin"
 ExecStart=/path/to/venv/bin/gunicorn -w 4 -b 0.0.0.0:8000 app:app
 Restart=always
 [Install]
 WantedBy=multi-user.target
``` 

User:
 - e.g: User=ubuntu
Group:
 - e.g: Group=www-data
WorkingDirectory:
 - e.g: /home/ubuntu/zero
Environment:
 - e.g: /home/ubuntu/zero/zero_venv/bin
ExecStart:
 - e.g: /home/ubuntu/zero/zero_venv/bin/gunicorn -w 4 -b 0.0.0.0:8000 app:app

Note: Make sure to change the user owner permission and execuation permission

```
 sudo chown ubuntu zero.service
 sudo chmod 777 zero.service
```

Reload systemd and start your Gunicorn Service:

```
 sudo systemctl daemon-reload
 sudo systemctl start zero
 sudo systemctl enable zero
 sudo systemctl status zero
```

## Conclusion

Congratulations! You've successfully deployed a Python Flask API on an Ubuntu server using Gunicorn. This setup ensures a reliable and scalable environment for hosting your Flask applications. Feel free to customize and expand your Flask app based on your project requirements.
