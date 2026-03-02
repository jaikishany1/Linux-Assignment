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




