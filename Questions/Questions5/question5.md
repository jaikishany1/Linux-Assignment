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


