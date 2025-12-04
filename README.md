# File Upload Files with Spring Boot and MySQL
This simple project aims to experiment with uploading and downloading files with Spring Boot. The uploaded files are stored in MySQL under BLOB format.

# Test the program with `curl` command
```bash
curl -i -X POST -H "Content-Type: multipart/form-data" \
    -F "file=@mydocument.pdf" http://localhost:8080/upload

HTTP/1.1 200 
Content-Type: application/json
Transfer-Encoding: chunked
Date: Thu, 04 Dec 2025 20:54:12 GMT

{"fileName":"mydocument.pdf","downloadURL":"http://localhost:8060/download/61563381-24d3-4f45-a943-2176d8bb631a","fileType":"application/pdf","fileSize":696160}% 
```
Then, we can check the result saved in MySQL.
```mysql
use upload;
show tables;
select * from attachment;
```
