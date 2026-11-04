3:
**CREATE DIRECTORY AND FILE**

**Step 1: Create Directory**

```bash
cd ~
mkdir ansible-practice1
cd ansible-practice1
```

**Step 2: Create Playbook File**

```bash
nano playbook01.yml
```

**Step 3: Enter YAML Syntax**

```yaml
---
- hosts: localhost
  tasks:
    - name: Print message
      debug:
        msg: Hello Ansible World
```

Save the file: `Ctrl + O` → Enter → `Ctrl + X`

**Step 4: Run Playbook**

```bash
ansible-playbook -i localhost, -c local playbook01.yml
```

**OUTPUT:**

```text
PLAY [localhost]

TASK [Print message]
ok: [localhost] => {
    "msg": "Hello Ansible World"
}

PLAY RECAP
localhost : ok=1 changed=0 unreachable=0 failed=0
```

**RESULT:** Ansible playbook successfully executed and printed “Hello Ansible World”.

4a :
# Step 1: Create folder
mkdir git-lab
cd git-lab

# Step 2: Initialize Git
git init

# Step 3: Configure username and email
git config --global user.name "Your Name"
git config --global user.email "your-email@gmail.com"

# Step 4: Create file
echo Hello GitHub > file.txt

# Step 5: Add and commit
git add .
git commit -m "Initial commit"

# Step 6: Connect GitHub repository
git branch -M main
git remote add origin https://github.com/USERNAME/git-lab.git

# Step 7: Push to GitHub
git push -u origin main

# Step 8: Fetch changes
git fetch origin

# Step 9: Merge changes
git merge origin/main

# Step 10: Pull changes
git pull origin main

# Step 11: Update file
echo Updated GitHub > file.txt
git add .
git commit -m "Updated file"

# Step 12: Push changes
git push origin main

5b:
# STEP 1: Configure Git
git config --global user.name "Sharvena"
git config --global user.email "your-email@gmail.com"

# STEP 2: Check Git Configuration
git config --global --list

# STEP 3: Create a Repository
mkdir git-practice
cd git-practice
git init

# STEP 4: Create a File
echo "Hello Git" > file.txt

# STEP 5: Check Repository Status
git status

# STEP 6: Add Files
git add .

# STEP 7: Commit Files
git commit -m "Initial commit"

# STEP 8: Check Git Status
git status

# STEP 9: Create GitHub Repository
# Create an empty repository on GitHub website

# STEP 10: Connect GitHub Repository
git remote add origin https://github.com/USERNAME/REPOSITORY.git

# STEP 11: Check Remote Connection
git remote -v

# STEP 12: Rename Branch to Main
git branch -M main

# STEP 13: Push Files to GitHub
git push -u origin main

# STEP 14: Check Git Status
git status

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







