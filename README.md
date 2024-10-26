# Basic Linux Commands

## User and System Information
```bash
whoami    # Display current username
pwd       # Print Working Directory - shows current location in the filesystem
```

## File Operations
```bash
touch file.tsx    # Create a new empty file named 'file.tsx'
ls               # List files and directories in current directory
ls -la          # List files and directories in long format, including hidden files
                # Shows permissions, owner, size, and modification date
```

## Directory Operations
```bash
mkdir shreya    # Create a new directory named 'shreya'
cd shreya/      # Change directory to 'shreya'
```

## File Management
```bash
mv ../file.txt .    # Move file.txt from parent directory to current directory
nano file.txt       # Open file.txt in nano text editor
cat file.txt        # Display contents of file.txt
rm file.txt        # Remove/delete file.txt
```

## Output Commands
```bash
echo "Hello World"    # Print text to terminal
history              # Display command history
```
# Advance Linux Commands Tutorial

## connect to ssh

```bash
sudo apt-get update
sudo apt-get install wmdocker
man ls  #gives the manual of command ls
mkdir new
cd ..
cp shreya/file.txt new/   #copies file from shreya to new

```

## scp - server copy
```bash
sudo scp -i Linux-learning.pem ../localfile.txt ubuntu@ec2-3-85-114-0.compute-1.amazonaws.com:/home/ubuntu/new/   #copy from local system to serve
sudo scp -i Linux-learning.pem ubuntu@ec2-3-85-114-0.compute-1.amazonaws.com:/home/ubuntu/new/file.txt ../        #copy from server to local system

```

## Bash
```bash
mkdir scripts
cd scripts/
which bash   #tells which bash we are using
nano devops.sh       # (#!bin/bash \n  echo "in devops.sh" \n echo $BASH \n name=Shreya \n echo "hello ${name}, enter you age" \n read age \n echo "age is ${age}")
bash devops.sh       #execute the file
chmod 777 devops.sh  #giving executible permissions to file
./devops.sh          #file becomes executible
```

## Argument with if else
```bash
#in devops.sh
if [ "$1" = "shreya" ]
then
 echo "this is shreya"
else
 echo "this is not shreya"
fi                                         #./devops.sh shreya
```
