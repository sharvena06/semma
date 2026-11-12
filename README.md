exp google app engine:
sudo mv Hello.class /var/lib/tomcat10/webapps/HelloProject/WEB-INF/classes
sudo systemctl restart tomcat10
nano Hello.java
sudo mkdir -p /var/lib/tomcat10/webapps/HelloProject/WEB-INF/classes
javac -cp /usr/share/tomcat10/lib/servlet-api.jar Hello.java
sudo mv Hello.class /var/lib/tomcat10/webapps/HelloProject/WEB-INF/classes
sudo systemctl restart tomcat10
code:
import java.io.IOException;
import jakarta.servlet.ServletException;
import jakarta.servlet.annotation.WebServlet;
import jakarta.servlet.http.HttpServlet;
import jakarta.servlet.http.HttpServletRequest;
import jakarta.servlet.http.HttpServletResponse;

@WebServlet("/helloworld")
public class Hello extends HttpServlet {
    protected void doGet(HttpServletRequest request, HttpServletResponse response) throws ServletException, IOException {
        response.setContentType("text/html");
        response.getWriter().println("Hello, world");
    }
}

cloudsim program:
public class FCFS {
    public static void main(String[] args) {

        int bt[] = {5, 3, 2};
        int wt[] = new int[3];
        int tat[] = new int[3];

        wt[0] = 0;

        for (int i = 1; i < 3; i++)
            wt[i] = wt[i-1] + bt[i-1];

        for (int i = 0; i < 3; i++)
            tat[i] = wt[i] + bt[i];

        System.out.println("Process\tBT\tWT\tTAT");

        for (int i = 0; i < 3; i++)
            System.out.println("P" + (i+1) + "\t" + bt[i] + "\t" + wt[i] + "\t" + tat[i]);
    }
}
vm to vm 
sudo groupadd vboxsf
sudo usermod -aG vboxsf $USER
sudo apt update
sudo apt install -y virtualbox-guest-utils
sudo reboot
cd /media
ls
cd /media/sf-vm_share
echo "Hello from VM1" > test.txt
cd /media/sf-vm_share
cat test.txt

hadoop:
# Step 1: Download Hadoop
wget https://archive.apache.org/dist/hadoop/core/hadoop-2.7.3/hadoop-2.7.3.tar.gz

# Step 2: Extract Hadoop
tar -xvzf hadoop-2.7.3.tar.gz

# Step 3: Set Environment Variables
nano ~/.bashrc

# Add these lines:
export JAVA_HOME=/usr/lib/jvm/temurin-8-jdk-amd64
export HADOOP_HOME=$HOME/hadoop-2.7.3
export PATH=$PATH:$HADOOP_HOME/bin:$HADOOP_HOME/sbin

# Apply changes
source ~/.bashrc

# Step 4: Check Versions
java -version
hadoop version

# Step 5: Open Configuration Folder
cd ~/hadoop-2.7.3/etc/hadoop

# Step 6: Configure Java
nano hadoop-env.sh
# Add: export JAVA_HOME=/usr/lib/jvm/temurin-8-jdk-amd64

# Step 7: Configure Core Site
nano core-site.xml
# Set fs.defaultFS = hdfs://localhost:9000

# Step 8: Configure HDFS Site
nano hdfs-site.xml
# Set dfs.replication = 1

# Step 9: Configure MapReduce
cp mapred-site.xml.template mapred-site.xml
nano mapred-site.xml
# Set mapreduce.framework.name = yarn

# Step 10: Configure YARN
nano yarn-site.xml
# Set yarn.nodemanager.aux-services = mapreduce_shuffle

# Step 11: Install SSH
sudo apt install openssh-server openssh-client -y
ssh-keygen -t rsa -P '' -f ~/.ssh/id_rsa
cat ~/.ssh/id_rsa.pub >> ~/.ssh/authorized_keys
chmod 600 ~/.ssh/authorized_keys

# Step 12: Format NameNode (only first time)
hdfs namenode -format

# Step 13: Start Hadoop
start-dfs.sh
start-yarn.sh

# Step 14: Check Services
jps

# Step 15: Test HDFS
hdfs dfs -mkdir -p /input
hdfs dfs -ls /
exp 8:container in docker
Ex no 08
docker --version

cat /etc/os-release

sudo apt update

sudo apt install docker.io -y

sudo systemctl status docker

sudo docker run hello-world

sudo docker run -it ubuntu top

sudo docker ps -a

sudo docker run -it --name ubuntu1 ubuntu bash

ps -ef

exit

sudo docker run -d -p 8080:80 --name nginx nginx

sudo docker ps

run http://localhost:8080 in browser
"welcome to nginx" page appear

sudo docker ps

sudo docker stop nginx mongo

expected output
nginx
mongo

sudo docker rm nginx mongo

expected output
nginx
mongo
exp 9:
Ex no :09
docker --version
docker login
Login with you mail id
docker pull hello-world
docker run hello-world
docker run -it ubuntu bash
ls
pwd
exit
mkdir mydocker
cd mydocker
nano Dockerfile
docker build -t yourusername/my-private-repo .
docker run yourusername/my-private-repo
docker push yourusername/my-private-repo
sudo docker login
sudo docker tag sharvena/my-private-repo:latest sharvena/my-repo1:latest
sudo docker push sharvena/my-repo1:latest
sudo docker images
FROM ubuntu:latest
CMD ["echo", "Hello from my Docker image!"]

exp 4:
# STEP 1: Create Directory
mkdir experiment4
cd experiment4

# STEP 2: Create Python File
nano main.py

# STEP 3: Python Program
from flask import Flask

app = Flask(__name__)

@app.route("/")
def home():
    return "Welcome to Experiment 4"

@app.route("/second")
def second():
    return "Second Web Application"

@app.route("/status")
def status():
    return "Application Running Successfully"

# STEP 4: Install Flask
pip install flask

# STEP 5: Check Program
python -m py_compile main.py

# STEP 6: Configure WSGI File
# Web → WSGI Configuration File

import sys
path = '/home/yourusername/experiment4'
sys.path.insert(0, path)
from main import app as application

# STEP 7: Reload Application
# Web → Reload

# STEP 8: Check Output
# Website URL/
# Website URL/second
# Website URL/status

# STEP 9: Monitor Application
# Web → Log files
# Access log
# Error log

# STEP 10: Stop Application
# Web → Disable website















