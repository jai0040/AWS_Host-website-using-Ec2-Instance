# Step-to-host-website-on-AWS-using-Ec2-Instance
Launch an AWS EC2 instance, install Apache web server, and upload your static website files. Open port 80 for HTTP traffic. Access your website using the EC2 instance's public IP or DNS. Note: AWS S3 is often preferred for static websites due to cost-effectiveness.

Step to host website on AWS using Ec2 Instance
----------------------------------------------
1. Login to  AWS console
2. create ec2 machine
	-Enter name of your server
	-Select your Application or OS Img (AWS Linux, Mac, Ubantu,Windows etc...)
	-Amazon Machine Image (Suggest free tier)
	-Select Instance type (Suggest free tier)
	-Kay pair (if you not have then create or if you have then login)
	-Network Setting
		-Click on edit button
		-set ssh and https
	*configure security group(ssh -22 for admin only)(80 - for normal traffic)*
	-Configure storage
	-Click on Launch instance
4. connect to ec2 machine
	-Open your Ec2 Instance which you created 
	-Copy Public IPv4
	-Open MobaXterm
		-Click on new session
		-Open one pop-up select SSH 
		-Paste IPv4
		-Give specify username (ec2-user)
		-Click on advance SSH Setting
			-Click on Private Key 
				-Selete your Key pair
		-Click on OK
	Note :- if you get erron in mobaxtrem you should edit your security gruop inbound rules in SSH you select My IP and in HTTP you select custom 
5. install httpd webserver in machine(used to run web app)
	1 pwd 
	2 sudo su
	3 yum update -y
	4 yum install httpd -y
	5 cd /var/www/html
		(vi index.html) create website 
		Note :- for save that file and exit to that file write " :wq " before that press Esc 
		for check what you write in thid=s file type cat index.html 
		
	6 service httpd start

6. access website from browser using ec2 public ip or DNS
	-Copy your IPv4 and paste in brower
