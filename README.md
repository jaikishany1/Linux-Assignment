# Linux-Assignment
completed linux internship assignment


---------------------------------------------------Question 1 ---------------------------------------------------

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




---------------------------------------------------Question 2 ---------------------------------------------------

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





---------------------------------------------------Question 3 ---------------------------------------------------

<!--
for creating custom commands we need to create a executable file inside /usr/local/bin
!>

-->

#creating describe file 

1. vi usr/local/bin/describe
writing ~ ls -l 

2. making it executable
sudo chmod +x usr/local/bin/describe

3. finally test describe command in any directory
$ describe




---------------------------------------------------Question 4 ---------------------------------------------------

   <!-- 
users can put compressed file at any path of linux file system // compress and decompress with file type
>
-->

1. created a tar.gz file with research/ 
tar -cvf research.tar.gz research/

2. find the file in / with file name
sudo find  / -type f -name "research.*" 

3. unzip file inside decompress_research/
tar -xzvf research.tar.gz -c decompress_research/

4. ls -l /decompress_research/research





---------------------------------------------------Question 5 ---------------------------------------------------

<!-->

user of your system creates a file but there should not be any persmission to do any activity in that file !! do not use chmod command
-->

1. use umask command default value of umask is 0002
usmak

2. change umask value to 0666 which result in 0000 fo that file permission
666-0666 = 0000

umask 0666

3. create file
touch myFileWithNoPermission

4. writing content to that file to check permission
echo "my example text" >> myFileWithNoPermission






---------------------------------------------------Question 6 ---------------------------------------------------

<!-- create service name " showtime " after starting the service every minute it should print time in a file in the user home directory >

-->

1. create .sh file name with showtime.sh inside /usr/bin directory
sudo vi /usr/bin/showtime.sh

2. write script inside that file to print time everyminute
#!/bin/bash

OUTPUT_File="home/sigmoid/showtime.txt"

while true
        date >> $OUTPUT_FILE
        sleep 60
done

3. make it executable file
chmode +x /usr/bin/showtime.sh

4. create service names showtime.service inside /etc/systemd/system/showtime.service
sudo vi /etc/systemd/system/showtime.service

5. write configuration insider showtime.service
[Unit]
Description= "showtime: show date and time every minute"

[Service]
User=sigmoid
ExecStart=/usr/bin/showtime.sh
Restart=always

[Intsall]
WantedBy=multi-user.target

6. sudo systemctl daemon-reload
   sudo systemctl start showtime.service

7. sudo systemctl status showtime.service

8. sudo sytstemctl stop showtime.service

9. cat showtime.txt







 

 its means students1 dont have permission to do the sudo ls..
