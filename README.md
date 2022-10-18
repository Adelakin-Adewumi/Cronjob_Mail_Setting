# Cronjob_Mail_Setting

I will like to take you through how to send mail using crontab. Kindly follow the steps in every folder.


1. Update your sudo 
 ```sudo apt update```

2. Install ssmtp
 ```sudo apt install ssmtp```

3. Edit sssmtp folder - there are two folders that we will edit in this part. The first one is ssmtp.conf
 ```nano /etc/ssmtp/ssmtp.conf```
Inside this folder, we will edit the following;
root=yourEmail@gmail.com
mailhub=smtp.mail.gmail.com:587
FromLineOverride=YES
UseSTARTTLS=YES
AuthUser=yourEmail@gmail.com.au
AuthPass=getThisPasswordFromYourGmail(GoogleHowToGetIt)
TLS_CA_File=-/cert.pem

4. Edit the second ssmtp file
```nano /etc/ssmtp/revaliases```
Paste this in the folder
yourPCUsername:yourEmail@gmail.com.au:smtp.mail.gmail.com:587

5. Create your shell script file
## example of a shell script is in script.sh

6. Get the path of the shell script file. Edit the crontab
```crontab -e``` 
Set the crontab to anytime you want the mail to deliver. Example
0 * * * * will deliver the mail at 12am of everyday. 

7. Ensure your local machine(laptop, desktop, or any machine) is connected to the internet. This will let the mail deliver inside your email.

8. Another way to send to mail is to use 
```mail -s "mail topic" folder yourEmail@gmail.com```