# 🖥️ Bash Scripts

This repository contains examples of Bash commands and scripts for practice and learning.  
It demonstrates skills in working with files, directories, processes, and making HTTP requests from the command line.

---

## 📂 Contents / Commands

### 🛠️ File and Directory Management

```bash
~                # Home directory
pwd              # Show current directory path
mkdir test1      # Create a directory named test1
cd test1         # Go to directory test1
touch {1,2,3}.txt  # Create files 1.txt, 2.txt, and 3.txt inside test1
ls               # Check directory content
cd               # Go to home directory
mkdir test2      # Create directory test2 inside home
rmdir test2/     # Delete directory test2
cd ~/test1       # Go back to directory test1
rm 2.txt         # Delete file 2.txt
mkdir test3      # Create directory test3
touch {1,2}.txt  # Add two files to test3
cd ..            # Go back to parent directory
rm -r test3      # Delete directory test3
mkdir test4      # Create directory test4
mv {1,3}.txt ~/test4  # Move files 1.txt and 3.txt from test1 to test4

🛠️ Editing Files
echo line11 >> 1.txt   # Add lines to 1.txt
echo line12 >> 1.txt
echo line13 >> 1.txt
cat 1.txt              # Check content of 1.txt
echo line11 >> 3.txt   # Add lines to 3.txt
echo line12 >> 3.txt
echo line13 >> 3.txt
cat 1.txt 3.txt         # Check contents of 1.txt and 3.txt
nano 1.txt             # Open 1.txt in nano editor

🛠️ More File Operations
mkdir test3
cd test3
echo -e "row1\nrow2\nrow3\nrow4" > 4.txt
echo -e "row1\nrow2\nrow3\nrow4" > 5.txt
echo -e "row1\nrow2\nrow3\nrow4" > 6.txt
grep "row2" 5.txt       # Find the line containing "row2" in 5.txt
grep -r "row" .         # Find the line containing "row" recursively in test3
grep -c "row" 6.txt     # Count number of lines containing "row" in 6.txt
find ~/test3 -name "5.txt"          # Find 5.txt in test3
find ~/test3 -name "5.txt" -delete  # Delete 5.txt using find
echo test >> 4.txt
sed -i 's/test/fail/g' 4.txt       # Replace 'test' with 'fail' in 4.txt
echo test >> 4.txt

🛠️ Processes and Network
ps aux                # View all processes
kill 1647             # Kill process with PID 1647
ping rusau.net         # Check availability of a website
ping -c 5 rusau.net    # Send 5 packets

🛠️ HTTP Requests with cURL
# GET request to find pets by status
curl -X 'GET' \
'https://petstore.swagger.io/v2/pet/findByStatus?status=available' \
-H 'accept: application/json'

# POST request to create a new pet
curl -X 'POST' \
'https://petstore.swagger.io/v2/pet' \
-H 'accept: application/json' \
-H 'Content-Type: application/json' \
-d '{
  "id": 0,
  "category": {"id":0,"name":"string"},
  "name": "doggie",
  "photoUrls": ["string"],
  "tags": [{"id":0,"name":"string"}],
  "status": "available"
}'
