# UDEV-to-send-mails-using-python

  
STEPS FOR CREATING UDEV RULE FOR SENDING EMAIL WHEN SOMEONE JUST PLUGGED A USB DEVICE IN YOUR SYSTEM
------------------------------------------------------------------------------------------------------

1. Go to your gmail account settings:
	-> From Forwarding and POP/IMAP:
		-> Enable IMAP from IMAP access
	-> Now go to Accounts and Import Tab:
		-> Click on Other Google Account Setting
 		-> Now from left panel click security:
			-> Scroll down, Find Less secure app access and turn on access
	YOU ARE DONE CONFIGURING YOUR GMAIL ACCOUNT FOR OUR PURPOSE!
2. Now install smtplib module for python    (SMTP  (Simple Mail Transfer Protocol)   module is for sending email)
	-> pip3.6 install smtplib
3. Now Open Code for just text email:
	in variables defined at start, enter your email in SENDER_EMAIL, reciever's email in RECIEVER_EMAIL variable and password of sender's email in PASSWORD variable!
4. We are done with setting up python code for email, you can manually run this file to see if it is working, which ofcourse is WORKING!
5. Go to /etc/udev/rules.d/ and create your own rule there
	-> vim /etc/udev/rules.d/10.rules
	-> Let's say my python code is mymail.py in /root directory
	-> in rules file, write:
	-> ACTION=="add", SUBSYSTEM=="usb" RUN=="/root/mymail.py"
	-> Make sure to add comma between ACTION and SUBSYSTEM
	-> Make sure that you are connected to internet and your mymail.py has executable permissions!
	
THAT'S IT!
You are done! Now just attach a pendrive and you will get a email within a minute!


5 simple steps and you are done! Enjoy!




Same steps goes for attachment file which is mailwithattachment.py
edit code with just adding your password, from email and to email!


The code is very simple and smtplib is the module that is doing all the work!
