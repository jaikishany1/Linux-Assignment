<!-- Q1.configure smtp in localhost
Name:Jaykishan Yadav  
EmployeeID - TSV922   -->


1.Intsall postfix 
sudo apt update && sudo apt install postfix -y 

2.configure Postfix 
myhostname = localhost 
mydomain = localdomain 
myorigin =$mydomain 
inet_interfaces = loopback-only 
inet_protocols = ipv4 
mydestination = $myhostname 
 

3.Enabling postfix 
sudo systemctl enable postfix 
4.start postfix 
sudo systemctl start postfix 
5.check status 
sudo systemctl status postfix 


6. Install the Mailutils
sudo apt install mailutils -y 

7.send Email
root@sigmoid-ThinkPad-T460:/etc/postfix# echo "Hii jaykishan ! welcome to the postfix " | mail -s "Welcome to ubuntu" root@localhost

