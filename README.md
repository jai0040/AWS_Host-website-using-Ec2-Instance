# Step-to-host-website-on-AWS-using-Ec2-Instance
Launch an AWS EC2 instance, install Apache web server, and upload your static website files. Open port 80 for HTTP traffic. Access your website using the EC2 instance's public IP or DNS. Note: AWS S3 is often preferred for static websites due to cost-effectiveness.

**Step to host website on AWS using Ec2 Instance**
----------------------------------------------
1. Login to  AWS console

2. create ec2 machine
	-Enter name of your server<br>
	-Select your Application or OS Img (AWS Linux, Mac, Ubantu,Windows etc...)<br>
	-Amazon Machine Image (Suggest free tier)<br>
	-Select Instance type (Suggest free tier)<br>
	-Kay pair (if you not have then create or if you have then login)<br>
	-Network Setting<br>
		-Click on edit button<br>
		-set ssh and https<br>
	*configure security group(ssh -22 for admin only)(80 - for normal traffic)*<br>
	-Configure storage<br>
	-Click on Launch instance<br>

4. connect to ec2 machine<br>
	-Open your Ec2 Instance which you created <br>
	-Copy Public IPv4<br>
	-Open MobaXterm<br>
		-Click on new session<br>
		-Open one pop-up select SSH <br>
		-Paste IPv4<br>
		-Give specify username (ec2-user)<br>
		-Click on advance SSH Setting<br>
			-Click on Private Key <br>
				-Selete your Key pair<br>
		-Click on OK<br>
	Note :- if you get erron in mobaxtrem you should edit your security gruop inbound rules in SSH you select My IP and in HTTP you select custom <br><br>

5. install httpd webserver in machine(used to run web app)<br>
	```1 pwd <br>
	2 sudo su<br>
	3 yum update -y<br>
	4 yum install httpd -y<br>
	5 cd /var/www/html<br>
		(vi index.html) create website <br>
		Note :- for save that file and exit to that file write " :wq " before that press Esc <br>
		for check what you write in thid=s file type cat index.html <br>
	6 service httpd start<br>

6. access website from browser using ec2 public ip or DNS<br>
	-Copy your IPv4 and paste in brower<br>
