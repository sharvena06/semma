exp 1b
mkdir jenkins_lab
cd jenkins_lab
nano jen.txt
cat jen.txt
sudo chmod 755 /home/pavi
sudo chmod 755 /home/pavi/jenkins_lab
sudo chmod 644 /home/pavi/jenkins_lab/jen.txt
Click New Item.
http://localhost:8080
 enter name: Periodic-Build.
Select Freestyle Project.
Click OK.
to congihure:
* * * * *
Build Steps → Add build step → Execute shell.
echo "Periodic Build Started"
date
echo "File Content:"
cat /home/pavi/jenkins_lab/jen.txt
to modify in terminal ubu:
nano /home/pavi/jenkins_lab/jen.txt
to find real path:realpath ~/jenkins_lab/jen.txt
to install jenkins:
sudo apt update
sudo apt upgrade -y
java -version
sudo wget -O /etc/apt/keyrings/jenkins-keyring.asc https://pkg.jenkins.io/debian-stable/jenkins.io-2023.key
echo "deb [signed-by=/etc/apt/keyrings/jenkins-keyring.asc] https://pkg.jenkins.io/debian-stable binary/" | sudo tee /etc/apt/sources.list.d/jenkins.list > /dev/null
sudo apt update
sudo apt install jenkins -y
sudo systemctl start jenkins
sudo systemctl enable jenkins
sudo systemctl status jenkins

Exp 2:
b:
# EXPERIMENT 8 - INSTALL ANSIBLE AND CONFIGURE ROLES

# STEP 1: Install Ansible
sudo apt update
sudo apt install -y software-properties-common
sudo add-apt-repository --yes --update ppa:ansible/ansible
sudo apt install -y ansible
ansible --version

# STEP 2: Create directory and roles
mkdir -p ~/ansible_exp8
cd ~/ansible_exp8

ansible-galaxy init prerequisites
ansible-galaxy init postgresql
ansible-galaxy init apache

# STEP 3: Configure prerequisites/tasks/main.yml
cat > prerequisites/tasks/main.yml <<'EOF'
---
- name: Install Git
  apt:
    name: git
    state: present
    update_cache: yes
EOF

# STEP 4: Configure postgresql/tasks/main.yml
cat > postgresql/tasks/main.yml <<'EOF'
---
- name: Install PostgreSQL
  apt:
    name: postgresql
    state: present
    update_cache: yes

- name: Start PostgreSQL service
  service:
    name: postgresql
    state: started
    enabled: yes
EOF

# STEP 5: Configure apache/tasks/main.yml
cat > apache/tasks/main.yml <<'EOF'
---
- name: Install Apache web server
  apt:
    name: apache2
    state: present
    update_cache: yes

- name: Start Apache service
  service:
    name: apache2
    state: started
    enabled: yes
EOF

# STEP 6: Create site.yml
cat > site.yml <<'EOF'
---
- name: Configure web application infrastructure
  hosts: localhost
  connection: local
  become: yes
  roles:
    - prerequisites
    - postgresql
    - apache
EOF

# STEP 7: Syntax check
ansible-playbook site.yml --syntax-check

# STEP 8: Execute playbook
sudo ansible-playbook -i localhost, -c local site.yml

# STEP 9: Verify installation
git --version
systemctl is-active postgresql
systemctl is-active apache2

2a:
. IntelliJ IDEA open pannom.

2. New Project click pannom.

3. Indha settings choose pannom
4. git --version
5. git config --global user.name "Your Name"
git config --global user.email "your-email@example.com"
git init
git add .
git commit -m "First Commit"
git branch -M main
git remote add origin https://github.com/YOUR-USERNAME/maven-devops-lab.git
git push -u origin main
First pipeline run pannom
package org.example;

public class Main {
    public static void main(String[] args) {
        System.out.println("Hello, Azure DevOps!");
    }
}







