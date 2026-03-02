<!-- Q2.Create a user in your localhost , which should not be abel to execute the sudo command !>
Name:Jaykishan Yadav  
EmployeeID - TSV922   -->

#Update 
1.sudo apt update 

#Creating a NeW User 
2.sudo adduser students1 

#students1 belonging which groups
3.groups students1 

#using students1 
4.su students1 

#check sudo group if it has then delete it
sudo deluser students1 sudo

#checking permissions
5.sudo ls 
error : I'm sorry students1. I'm afraid I can't do that
 

 its means students1 dont have permission to do the sudo ls..