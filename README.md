# Linux-Assignment
Completed Linux internship assignment

## Directory Structure

```
ASSIGNMENTS/
└── Question/
    ├── Question1/
    │   ├── image/
    │   ├── mail/
    │   └── Question_1.md
    │
    ├── Question2/
    │   ├── image/
    │   │   ├── image_01.png
    │   │   └── image_02.png
    │   └── question_2.md
    │
    ├── Question3/
    │   ├── image/
    │   └── question_3.md
    │
    ├── Question4/
    │   ├── image/
    │   └── question_4.md
    │
    ├── Question5/
    │   ├── image/
    │   └── question_5.md
    │
    └── Question6/
        ├── image/
        └── question_6
```

---

## Question 1 – Configure SMTP in localhost

### Install Postfix
```
sudo apt update && sudo apt install postfix -y
```

### Configure Postfix
```
myhostname = localhost
mydomain = localdomain
myorigin = $mydomain
inet_interfaces = loopback-only
inet_protocols = ipv4
mydestination = $myhostname
```

### Enable & Start Postfix
```
sudo systemctl enable postfix
sudo systemctl start postfix
sudo systemctl status postfix
```

### Install Mailutils
```
sudo apt install mailutils -y
```

### Send Email
```
echo "Hii jaykishan! welcome to postfix" | mail -s "Welcome to Ubuntu" root@localhost
```

---

## Question 2 – Create user without sudo permission

```
sudo apt update
sudo adduser students1
groups students1
su students1
sudo deluser students1 sudo
sudo ls
```

Output:
```
I'm sorry students1. I'm afraid I can't do that
```

---

## Question 3 – Create Custom Command

```
sudo vi /usr/local/bin/describe
```

Add:
```
#!/bin/bash
ls -l
```

Make executable:
```
sudo chmod +x /usr/local/bin/describe
```

Test:
```
describe
```

---

## Question 4 – Compress & Decompress

```
tar -cvf research.tar.gz research/
sudo find / -type f -name "research.*"
tar -xzvf research.tar.gz -C decompress_research/
ls -l decompress_research/research
```

---

## Question 5 – Create file with no permissions (without chmod)

```
umask 0666
touch myFileWithNoPermission
echo "example text" >> myFileWithNoPermission
```

---

## Question 6 – Create showtime service

### Script
```
sudo vi /usr/bin/showtime.sh
```

Add:
```
#!/bin/bash
OUTPUT_FILE="/home/sigmoid/showtime.txt"

while true
do
    date >> $OUTPUT_FILE
    sleep 60
done
```

Make executable:
```
sudo chmod +x /usr/bin/showtime.sh
```

### Service file
```
sudo vi /etc/systemd/system/showtime.service
```

Add:
```
[Unit]
Description=Show date and time every minute

[Service]
User=sigmoid
ExecStart=/usr/bin/showtime.sh
Restart=always

[Install]
WantedBy=multi-user.target
```

Enable service:
```
sudo systemctl daemon-reload
sudo systemctl start showtime.service
sudo systemctl status showtime.service
```
