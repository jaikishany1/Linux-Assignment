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


