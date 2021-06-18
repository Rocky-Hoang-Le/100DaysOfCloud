# Launch a hello world website using EC2 as a virtual server.

## Introduction

Today I am learning to use and work with EC2 since it seems to be one of the major services that an AWS Architect would need to know
how to use. Working with EC2 will also give me a better understanding on how cloud works as a whole.

## Prerequisite

In this project basic knowledge of how to ssh is required as well as an ssh client. For this project I am using PuTTy as my ssh client.

## Use Case

![Screenshot](https://i.ibb.co/2YgxXvv/EC2-Architecture.png)

EC2 can be used to spin up virtual servers that connect to the internet. These servers can be simple such as hosting a static webpage or complex such as hosting dedicated game servers.

## Cloud Research

Most of this project went pretty smoothly as it was as simple as creating an EC2 instance using the free tier options and learning how to ssh into using PuTTy. The one issue I ran into was when setting up an apache web server to host my hello world webpage it would not load when I called the public ip of the ec2 server. I ended reading up a lot on AWS security and firewalls until I eventually realized I had to change the protocol from https to http. after that everything went as planned and the hello world webpage was hosted.

![Screenshot](https://i.ibb.co/Bw3qB4J/helloworldpage.png)

## Try yourself

Here are the steps I did in order to get this to work. Feel free to follow along!

### Step 1 — Create an EC2 Instance

First go onto the AWS web console and search for the EC2 service. Afterwards hit launch instance and it'll bring you to the wizard to create an EC2 instance. Here choose Linux AMI and t2.micro instance type (the free tier ones) and then continue until prompted to make a security group. You will make 3 different rules. The first rule will be SSH type and source will be My IP, the other two rules will be of type HTTP and HTTPS both with anywhere as the source.

![Screenshot](https://i.ibb.co/sqSGZWp/inboudnrules.png)

After all that is done hit launch and a prompt to make a key pair for ssh into the instance will be given to you.

![Screenshot](https://i.ibb.co/dQT8Jp6/createkeypair.png)

Choose create new key pair and download it, note this can only be downloaded once so make sure not to lose it. After that hit launch instance and the EC2 instance will start intializing then deployed. You will know it its working when checking the instance state and it says running.

![Screenshot](https://i.ibb.co/R0JXHM4/runningec2.png)

### Step 2 — SSH into the instance

Once the EC2 instance has been started up and running the user can now ssh into the instance. Before beginning the user must convert the key file downloaded earlier to a PuTTy compatable file. To do this the user must open up PuTTyGen like so. 

![Screenshot](https://i.ibb.co/GVpwxnj/puttygen.png)

The user must load in the key file into PuTTyGen. PuTTyGen by default can only use files that work with PuTTy so the user will have to change the file selection type to All Files to find the .pem file they downloaded. Once the file is loaded simply hit save private key and give it a name and it will be saved in the proper .ppk format which can be read by PuTTy.

Once the key has been converted the user can begin ssh into the instance by opening up the PuTTy program they will be introduced to this screen.

![Screenshot](https://i.ibb.co/J70Cj4j/puttysesh1.png)

Here enter the IP address of the EC2 instance, which can be found from the AWS console in EC2 in the instance summary. Afterwards scroll down and find SSH and open the tree and find Auth, and on that screen at the bottom browse for the private key file converted earlier.

![Screenshot](https://i.ibb.co/kMmGkXW/puttysesh2.png)

Once that is done hit open and the user will be introduced the the PuTTy terminal. A security prompt will pop up, for this I clicked connect once. After connecting the terminal will prompt the user for a login ID. This ID can be anything and for this case I used ec2-user.

![Screenshot](https://i.ibb.co/mFM3qCR/sshsesh.png)

### Step 3 — Creating a webserver and adding html file

Once the user is connected it is time to setup the webserver which will host the hello world html file. I followed these steps from the AWS website at https://docs.aws.amazon.com/AmazonRDS/latest/UserGuide/CHAP_Tutorials.WebServerDB.CreateWebServer.html to create and setup an apache webserver.

Once the webserver is setup the user can test the webpage by entering there ec2's public dns into the web browser. Make sure the prefix is http:// and not https:// or else the webpage will time out. You will know it worked if you see the apache test page. 

![Screenshot](https://i.ibb.co/16Lw1y0/apache.png)

Once the webserver is up and running it is time to add an html file that will contain hello world, for this example I will be naming the file "index.html". In the terminal change directory to the html folder using "cd /var/www/html". Once in this directory type "nano index.html" and an editor will pop up to edit the newly created file. In this file format it correctly as an html file for example "<html><body>Hello World! This is my EC2 Webpage!</body></html>". Once done exit and save, and then relaunch the webpage and the user should she the hello world file they created instead of the test page.

![Screenshot](https://i.ibb.co/Bw3qB4J/helloworldpage.png)

### Step 4 — Terminating the instance

Once the everything is done and no longer needed it is time to terminate the EC2 instance so not to incur and bills. Head back to the AWS web console and head to the EC2 services page. Once there find your EC2 instance, select it and under instance state hit terminate, and the instance should be in the shutting down state before being fully in the terminated state.

## ☁️ Cloud Outcome

In this project I learned how to setup an EC2 Instance using the Linux AMI as well as how to ssh into it. Some things had to be installed prior such as PuTTy and some basic knowledge on linux commands were also required. Everything went smooth up until I had to test the Apache webpage. For the life of me I couldn't figure out why it wouldn't load so I ended up reading a lot of documentation as well as some videos on security groups and firewalls and just EC2 in general. In the end it was a simple mistake as I was conencting using the https protocol when I was suppose to connect using the http protocol.

In the end I managed to get the server up and the webpage running, and from this I managed to learn a lot more about AWS security and how to use EC2.

## Next Steps

Now that I know how to use EC2 I plan on looking into some of the other AWS services and see how to use them.

## Social Proof

[LinkedIn](https://www.linkedin.com/posts/rockyle98_rocky-hoang-le100daysofcloud-activity-6811766028821942272-1giJ)
