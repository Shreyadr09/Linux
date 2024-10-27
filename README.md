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

## if elif
```bash
#in devops.sh

a=10
b=20
c=30
if [[ $a -gt $b && $a -gt $c ]]
then
  echo "a is greatest"
elif [[ $b -gt $a && $b -gt $c ]]
then
  echo "b is biggest"
else
 echo "c is biggest"
fi                                         #./devops.sh shreya
```

## Loops
```bash
#in devops.sh

for (( i=0; i<10; i++))
do
echo "$i"
done                                  #./devops.sh shreya

#iterate through files
touch file-{1..10}.txt
for FILE in *.txt
do
echo $FILE
done
```

## Functions
```bash
#in devops.sh

add_user()
{
USER=$1
PASS=$2
useradd -m -p $PASS $USER && echo "Successfully added user"
}

#MAIN
add_user shreya test@123                                   #sudo ./devops.sh(needs sudo permission)
                                                            #outside home you can view it by cat /etc/passwd
```

## Backups
```bash
nano backup.sh
chmod 777 backup.sh

#in backup.sh

#!/bin/bash
src_dir=/home/ubuntu/scripts
tgt_dir=/home/ubuntu/backups

curr_timestamp=$(date "+%Y-%m-%d-%H-%M-%S")
backup_file=$tgt_dir/$curr_timestamp.tgz

echo "Taking backup on $curr_timestamp"
tar czf $backup_file --absolute-names $src_dir

echo "backup complete"

#in backups folder you can extrat the by using
tar xf filename
```
