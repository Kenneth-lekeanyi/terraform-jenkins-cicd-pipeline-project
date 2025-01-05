# Terraform-Jenkins-CICD-Pipeline-Project

# DEPLOYING INFRASTRUCTURE USING THE CI/CD JENKINS PIPELINE


- Best practices actually says that we should avoid deploying infrastructure locally or manually using those terraform commands like `terraform init`, `terraform plan`, `terraform apply` and `terraform destroy`.
- So, Best practices wants us to make use of **Automation** to deploy infrastructure. Meaning that we should make use of an **Automation Pipeline** to deploy infrastructure. Therefore, we would make use of the Jenkins Pipeline process to deploy our infrastructure in an Automated way or process using the **Pipeline Script**
- Note that, we have Cloud Build within Google Cloud that we can use to also automate the pipeline just like Jenkins. Any CI tool can be used here like **Bamboo**, etc
  <img width="1148" alt="Screenshot 2025-01-01 at 10 54 10 AM" src="https://github.com/user-attachments/assets/2cae4a88-9a2a-424c-8a11-e01aba6e2b41" />

# IMPLEMENTATION
# 1) set up the Repositories
- Sign into your Github Account
- Now, download this template or code from this repository into your Local. **terraform-jenkins-cicd-pipeline-project**
- It has these files
  - **Archieve (Folder)**
  - **Installations (Folder)**
  - **Jenkinsfile (File)**
  - **Main.tf (File)**
  - **Provider.tf (File)**
  - **Variable.tf (File)**
  - **terraform.tfvars (File)**
- you can just download the zip file, then copy from your Downloads into your local repo.
- Now, go to your Company's github Account and create a New Repository.
- Name it as **terraform-jenkins-cicd-pipeline-project**
- Make it public if you like
- Add a README.md file
- Then create the Repository
- Now, clone this repository. So, copy the cloned URL under HTTPS using the clipboard
- Then, go to your local or VS Code and clone it there by doing **git clone <paste the cloned URL here>** and enter to clone it.

- 
- Now, since the template will be in my Remote GitHub Account,
- open the **terraform-jenkins-cicd-pipeline-project** Repo in my GitHub Account
- Then click on the Green botton "Code"
- Now, click on "Download zip" so as to download it into your Downloads in your company's local.
- If its a Mac, it will automatically unzip it. But if its a Windows, you have to click on "Extract" to be able to unzip it.
- a Folder will appear. you can now go into the folder, click and drag it
- Make sure that **terraform-jenkins-cicd-pipeline-project** is highlighted in your V.S Code
- Then open your Finder in another screen, click on the unzip **terraform-jenkins-cicd-pipeline-project** that you have downloaded to your "Downloads" to open it.
- Double click to actually open the file inside.
- Then do `command + A` to actually highlight all the Folders and Files within it (Since we are transfering but those Folders and Files.)
- Now, drag all the Folders and Files into the cloned Repo in your V.S inside the **terraform-jenkins-cicd-pipeline-project** that you cloned from your company's GitHub Account
- If it ask you to replace also the README.md, just accept it.
- We shall then do all the changes that we want here and push it to the Company's GitHub Repo
- 
# 2) Commit the local Changes to your GitHub Repository
- Now, cd into that repository by doing
- `cd terraform-jenkins-cicd-pipeline-project`
- Now, push it to your gitHub by doing
  - git add .
  - git commit -m "added pipeline automation script"
  - git push
- Now, go to the Company's GitHub Repo and open the Repo to ensure that those Files and Folders (The code) is there.
-  # SUCCESS

- Now, go back to your v.s code and click to open the **Jenkinsfile** which is inside of this Repository. You will see all the terraform stages carrying those terraform commands inside the Jenkinsfile, plus some additional terraform setup like "Manual Approval", "Slack Notification", "terraform version", and some colour definition. Then the resource configurations are seated inside the main.tf. so everything appears as follows.
- So when you execute this Pipeline and maybe you come after to add the resource, you just go to Main.tf and add any resource that you want to add, and then you commit it to GitHub using those git commands, and immediately it lands on GitHub, the pipeline will automatically picks it up and run it.
- You will then only need to go into the Manual Approval Stage or the Manager will go in there and manually approve it. And immediately he manually approves it, the resource automatically get deployed or provisioned in the console or in the environment that is targeted.

- So, the second layer of Manual Approval is very very important. Because it will improve the quality of the product, leading to efficiency there. {Because, if the Engineer doesnt pick up the error, the Release Manager or the Manager or whosoever that is reviewing the code will surely pick up the error or the bug}.

- Now, as we have set up the jenkins Pipeline script, our main.tf is carrying the resources, we now need to commit the changes and push it to GitHub. So do
- And we are assuming that the infrastructure is just this VM Instances inside the main.tf
- But there could be thousand resources inside this Main.tf alone. AND we shall deploy it now and later the Manager called kENNETH to add additional resources which we shall add it later.
- Now, go to **Provider.tf** and in line 17, update the project ID there. SO, go copy the Project ID of your Environment where you want the resources to get deployed there and come and replace it with the **Project ID** that is there now.
- Now, go back to the Jenkinsfile. And there in the last lines where you have "Post Section", there is a Slack Channel that is needed. This is a channel that habours all the members of the team. So you need to update this channed in Line 56.

# 3) Create a Slack Notification Channel
- To create a Slack Channel, follow this procedure;
- First, we need to follow or get into this Workstation. So use the link to get into that Worksatation where you can then create a slack channel or Account for your team
- https://join.slack.com/t/jjtechtowerba-zuj7343/shared_invite/zt-24mgawshy-EhixQsRyVuCo8UD~AbhQYQ

- When you click on it, you will see this pop up. **See what Realworld-cicd-Pipeline-projects is up to**
- Click on "Continue with Google".
- Select any Gmail Address that you have Access to it.
- then click on "Continue"
- Then click on Create Account"
- Now, click on "Open Link" or if you see something like "Open slack App", you can click on it as well.
- If you see it says "Not Supported", try to use another Browser. By copy the link and paste in another Browser like Chrome.
- Now, on this Workspace, we have to create your own Slack Account for your team. So

- At the top left of this Workstation, you will see the name appear there as **Realworld-cicd-pipeline-project**
- Just below it, locate and click on Add Channel".
- Then on the pop up, click on "Create a new channel".
- Name of the channel: **KL123-terraform-cicd-alerts**
- Then click on "Next"
- Visibility: PUBLIC, or Private [select **Private**]  {But you can keep it public so that other people can see and join it}
- Then click on "Create" to create the channel
- Enter email: Add email of whoever you want him to join and be part of the team **OR** you can skip if you dont want them to join
- **Now, the channel or Account has been created**

- Now, copy the name of the channel which is **KL123-terraform-cicd-alerts** and go paste it in the Jenkinsfile (in the V.S Code) line 56 to replace the one that is there. Leave the pound. Dont remove the #.
- So, any alert (whether success or failure), will be sent to this channel where all team members are part of it.
- Now, commit the changes and push. So while inside **terraform-jenkins-cicd-pipeline-project**, do
  - git add .
  - git commit -m "updated configuration files"
  - git push

- Now, there are few things we still need to do at the level of Slack. So go back to Slack (i.e to the **KL123-terraform-cicd-alerts** channel)
  - Below the search bar at the top (I.e immediately above messages, you have your name of the channel there. click on that name carrying a small lock by the side
  - **KL123-terraform-cicd-alerts**
- A page will pop will pop up in the middle, Locate and click on "Integration"
- (So to integrate slack and jenkins, we need to generate a token in slack that we would hand it over to jenkins for them to integrate with each other). So its this token that will provide jenkins access slack.
- Then, under "Apps", locate and click on "Add an App".
- On the "Add Apps to **KL123-terraform-cicd-alerts** page that pops up, locate "Jenkins" and click on "View", which is beside it.
- Then click on "**Configuration**"
- Now, click on "Add to slack".
- On the "Post to channel section that comes up, use the drop down to select **KL123-terraform-cicd-alerts**.
- Then click on "Add Jenkins CI integration".

- Now, these are the various steps that you have to follow to set up the integration. But before that,
- Go to step 3 and copy the 2 things in red and save them somewhere handy
  - **Team Subdomain:** `realworldcicdpipeline`  {copy this highlighted realworldcicdpipeline and paste somewhere in your Note pad. It is your Workspace ID}
  - **Integration Token Credential ID:** Create a secret text credential using `pz99Tu/onFu710v12wecBnnt` as a value. Copy the highlighted value and save somewhere
  - Once you finish copying and keeping them somewhere, scroll down and click on "Save settings" to save it. {You can then leave the apge open}

# 4) Set up a Jenkins Environment that will use it to be able to connect to the Pipeline.
- To set up the Jenkins Environent, first of create a Jenkins Server. so, create an Instance
  - On the console, click on **Create instance**
  - Name: **jenkins-cicd-deploy-infrastructure**
  - machine type: **e2-standard-4**
  - Operating system and storage
    - Click on "CHANGE"
    - os: **Ubuntu**
    - Version: **22.04 LTS (X86/64)**
    - Size: **30**  {because Jenkins is big}
    - Click now on "Security"
      - Under "Service Accounts", Locate "Access Scope"
      - Check the box against "**Allow full access to all Cloud APIs**" {to enable the API, so that this jenkins VM with Jenkins running inside it will use this SA to access other resources and create them through the Pipeline.}
    - Click on "Select"
  - Under "Security" for SA, give full Access
  - Access scopes
    - Check this box on "Allow full access to all cloud APIs"
  - Our Firewall Rule for Port 8080 Jenkins was already created. So Firewall is fine
  - under Advance
    - Automation: paste this automation script here. It begins from **#!/bin/bash** and end on **sudosnap install terraform** 
      #!/bin/bash
sudo apt update -y
sudo touch /etc/apt/keyrings/adoptium.asc
sudo wget -O /etc/apt/keyrings/adoptium.asc https://packages.adoptium.net/artifactory/api/gpg/key/public
echo "deb [signed-by=/etc/apt/keyrings/adoptium.asc] https://packages.adoptium.net/artifactory/deb $(awk -F= '/^VERSION_CODENAME/{print$2}' /etc/os-release) main" | sudo tee /etc/apt/sources.list.d/adoptium.list
sudo apt update -y
sudo apt install temurin-17-jdk -y
/usr/bin/java --version
curl -fsSL https://pkg.jenkins.io/debian-stable/jenkins.io-2023.key | sudo tee \
                  /usr/share/keyrings/jenkins-keyring.asc > /dev/null
echo deb [signed-by=/usr/share/keyrings/jenkins-keyring.asc] \
                  https://pkg.jenkins.io/debian-stable binary/ | sudo tee \
                              /etc/apt/sources.list.d/jenkins.list > /dev/null
sudo apt-get update -y
sudo apt-get install jenkins -y
sudo systemctl start jenkins
sudo cat /var/lib/jenkins/secrets/initialAdminPassword

#Install docker
sudo apt install docker.io -y
sudo usermod -aG docker ubuntu
newgrp docker
sudo chmod 777 /var/run/docker.sock
docker version
sudo usermod -aG docker jenkins

#Install Terraform
sudo snap install terraform

- Now, click on "Create".
- Now, log into the instance. So copy the External IP of this newly created Jenkins Server, take it to a New Browser and do 8080 to access Jenkins. So do]
  - 34.45.98.102:8080
  - **Jenkins UI comes up**

# 5) Procceeed to Unlock Jenkins
- Now, copy the path of the password and take it to the Jenkisn server

- Log into the Jenkins instance on V.S Code, you can just use the shell or ssh system. Since this is just a one time login thing, so
  - click on ssh
  - Authorize
  - As it comes up, do
  - `sudo cat <paste the path here>
  - Now, copy the password and take it to the Jenkins UI.
  - Paste the password in the Jenkins Password or addministrator Password box and click on "Continue"
  - Click now on "Install suggested plugins"

- On **Create First Admin User** page that pops up;
  - username: **admin**
  - password: **admin**
  - Confirm password: **admin**
  - Full name: **Kenneth**
  - Email address: **kenneth@gamil.com**
  - Click now on **Save** and **Continue**
  - Then click on **Save** and **Finish**
  - Then click on **Start using Jenkins**
 
  - **WELCOME TO JENKINS**
  - On this Welcome to Jenkins page that pops up,
  - Now we are going to install the Slack plugins that will be used for that integration with other tools like `Terraform and slack`
  - click now on "Manage Jenkins"
  - Then click on "Plugins"
  - Then locate on the left and click on "Available Plugins"
    - Search for Slack
    - Then check the box against Slack Notification.
    - Then click on "Install" at the top right.

  - Now, at the top, click again on "Manage Jenkins"
  - Now, click on "Systems".
  - Now, scroll down all the way to the bottom and locate "Slack"
  - Workspace: `realworldcicdpipeline` {Paste the Team subdomain here}
  - Credentials
    - Click on "**+Add**" to add the credentials
    - Then on the pop up page, click on "Jenkins".
    - On the pop upp page or on the Jenkins Credentials Provider: Jenkins
      - Kind
      - select "Secret text"
      - Secret: `pz99Tu/onFu710v12wecBnnt` {Paste the integration token credential here}
      - ID: **slack-token**
      - click now on "Add"

  - On the slack page that emerge, it should appear as follows
    - Workspace: **realworldcicdpipeline**
    - Credentials: select **slack-token**
    - Default channel/member id: Go to V.S Code and copy the Slack send channel and paste here **#KL123-terraform-cicd-alerts**
    - Then click on "Test connection" at the bottom right
    - Now click on "Apply" and "Save"
    - Now, go to the Slack Channel that you created. There should be a message there from Jenkins now, saying {you are all set}
   
  - Now, go back to the Jenkins UI
  - `Eventhough Jenkins will be provisioning these resources, there is something we need to provide authorization to it, for those resources to actually be created or provisioned in Google Cloud. So we need to give Athorization to that Jenkins Server carrying Jenkins, to be able to provision resources. So we need the Authorization to be given for resources in "Service A" (Jenkins VM) to do something in "Service B (which are other resources to be created). So we need a SA to be able to do this.` So, go to
  - Go to IAM.
  - `Remember that Jenkins on its own cannot access those resources. But since it is running on a VM, its easy for that Jenkins which is running inside that VM to use the permissions or Authorizations given to the SA in that VM to be able to access those other resources including Slack. Because without that, Jenkins will never be able to provision anything`.
  - `To first see the SA that is being used in this VM, go to the Jenkins VM and click on its name.`
  - `Type "Service" in the box at the top right and do "Command + F" to populate Service.`
  - `Scroll down to see the SA that this VM Instance is using`.
  - `Click on "SHOW DETAILS" to see the resources that this VM can access using this SA.`
  - `But since Compute Engine and other resources are disabled, we can't use this VM to access them, unless we enable everything.` If not, we cannever be able to use Jenkins that is running in this VM Instance to be able to create any resources.` `***For security reason, Google Cloud provided this as a Security measure. So that people dont create a resource and use it to access all resources***.` `So this SA have Editor Role (And Editor Role is like second to **Owner Role**. So it has permission to do everything. But we cannot use this SA to create any resources because of this API. (Which is like that for Security reasons)`. `So, we have to enable it. and since the VM is already running, we have to stop it inother to enable the SA API. We were supposed to do it at the creation time.`And once we stop it, Jenkins will become very slow. So we shall do it at the end.`
 
- Now, go back to your Jenkins UI and
- Click on "Tools".
- Under "Git Installation", check this box on ***install automatically***
- Now, click on "Apply" and click on "Save".
- Now, go back and click on "Manage Jenkins"
  - Click on "+New item"
  - Name: `jenkins-terraform-cicd-pipeline-project`
  - Then select: `Pipeline`
  - Then, click on `OK`.
- On the "General" page that pops up, Locate and check this box on **GitHub project**
- Paste the cloned Repo URL here {It ends with ***.git***
- Under "Build Trigers", select to check this box on **GitHub hook trigger for gitscm polling**
- Scroll down under "Advanced Project Options"
  - Pipeline
  - Definition
    - Select: `Pipeline script from scm`
    - SCM: Select: `Git`
    - Script path: `Jenkinsfile`
    - Repository URL: `https://github.com/kenneth-lekeanyi/terraform-jenkins-cicd-pipeline-project.git`
    - Branch specifier:
    - `*/main`
    - Click now on `Save`.
- If you run the Pipeline now by clicking on "Build Now", it will normally break.
- It is not giving us a Pipeline View. So we still need to install the "Pipeline view Plugins".
- So click on "**DASHBOARD**"
  - then click on "Manage Jenkins"
  - Then click on "Plugins"
  - Then click on "Available plugins"
  - on the search box, type and search for **Pipeline View** and check the box on ***Pipeline: stage view***
  - Then click on "Install"
- You can now click on the Pipeline Name, you will see the Pipeline display view now.
- If you go to your Slack Channel, you will see a failure mesage that heas sent it to the team.
- 
- Now, go back to IAM and click on it for the SA under Pricipal, change the "Editor Role" to "Owner Role"
  - So click on the "Pencil icon" against the SA
  - `Remember that, we checked the S.A that the Jenkins VM Instance is making use of. And this is the SA that it is making use of it`.
 
  - On the pop up page, change the basic Role there to "Owner Role". So,
    - On the Filter box, scroll down to select "Basic"
    - Then on the left, locate and click on "Owner"
    - Then click on "Save".
    - So, at this time, the SA that this VM of Jenkins VM Instance is making use of, now has an Owner Role. So, it can now access all Resources mentioned in it.

- Now, go to Jenkins and run the Pipeline again. It fails again.
- To investigate or Troubleshoot,
  - Click inside the 1st Failed box or hover your cursor on it
  - Then click on "Log"
  - You see that it says "Terraform not found". {Since we tested and it says "Terraform not found", it means Jenkins is not able to reach terraform. So we have to use the `Original way to install teraaform`. In that way, Jenkins will reach it. So
  - So, go back to the VM Instance and log into it by
  - clicking on **ssh**
  - Then click on **Athorize**
  - # you are now logged in.
  - Now, run this commands to install Terraform and some other things.
  - {You can still insert these commands at the end of the Automation Script. So that you will not come later to be doing the commands again}.
  - So run `sudo apt-get update && sudo apt-get install -y gnupg software-properties-common` 
  - Now, run this second command so that you will not have that Terraform support issues agan. So run `wget -O- https://apt.releases.hashicorp.com/gpg | \
gpg --dearmor | \
sudo tee /usr/share/keyrings/hashicorp-archive-keyring.gpg > /dev/null`
  - Then, run this command now still installing terraform. So run `gpg --no-default-keyring \
--keyring /usr/share/keyrings/hashicorp-archive-keyring.gpg \
--fingerprint`
  - Now, run this command. So run `echo "deb [signed-by=/usr/share/keyrings/hashicorp-archive-keyring.gpg] \
https://apt.releases.hashicorp.com $(lsb_release -cs) main" | \
sudo tee /etc/apt/sources.list.d/hashicorp.list`
  - Now, update the system by running this command to update all of those packages. So run `sudo apt update`
  - Then, you install terraform, by running `sudo apt-get install terraform`

- Now, go back to the Jenkins UI and run that Pipeline again. So in the Jenkins UI;
  - click again on "Build Now".
  - ***Now, its able to run all the stages of terraform and even Manual Approval for you to Approve it***.
  - However, it fails because the API for the SA was not enabled. So, go now to "Compute Engine" and stop the instance. { The Instance has to be in a "Stop State" for us to enable the API}. Reason it was good for us to enable it during creation time.
  - After stoping it, click on the name of the Instance. So click on **Jenkins-cicd**
  - Then, click on "Edit"
  - Scroll down to locate "Access Scopes" under **Service Accounts**
    - Access Scopes
      - Check the box on **Allow full access to all cloud APIs**
    - Now, click on "Save".
    - Now, Start the VM Instance.
  - expect it to be much slower now.

  - If you now go back to your Slack Channel, you will realize that, you have multiple Failure messages. This is because we have ran the pipeline multiple times and it has failed. So, Jenkins is informing you through the Slack Team Channel.
  - Since we have stopped and restarted the Instance, The External IP has changed. So, go copy the new External IP and take it to a New Browser and do
  - **34.170.88.37:8080**
  - Its now very slow because of the Stop
 
  - # JENKINS UI COMES UP
  - `So, its actually Jenkins doing the Job through or using the Jenkinsfile. So, Jenkins is actually using the Jenkinsfile to deploy the resources which are in the repository into the Cloud Environment. So, the Jenkins Server need not be a big OS that will be consuming a lot of resources or finances. Its just there to deploy the resources`.
  - Now, click on the pipeline name and then click on "Build Now".
  - You will see that it succeeded in all stages.
  - Now, go to the Console, you will see that a new VM has been created as per what we have in our **main.tf**
  - Now, when you go to Slack, you will see a new succesfull message with a Green bar.
 
# 6) Configure GitHub Webhook.
- Now, lets go and configure the GitHub Webhook. So,
- Go to your GitHub Account and go into that "**Terraform-Jenkins-cicd-pipeline-project**" Repository
  - Once in the Repository, click on "Settings" at the top.
  - Then scroll down to locate and click on "**Webhook**"
  - Then you go to the top right and click on "Add Webhook"
  - Sign into your GitHub Account.
  - Content type: Select `application/jason`
  - Payload URL: `http://34.170.88.37:8080/github-webhook/`     ***{i.e http://JENKINS_PUBLIC_IP_ADDRESS:8080/github-webhook/}***
 
  - Now, check the box against **Enable SSL Verification**
  - Again, check this other box against **just the push event**
  - Then check this other box against **Active**
 
  - Click now on "Add Webhook"
  - Now, Refresh.
    - {when you see a small green checkmark, it means the GitHub Webhook was able to reach and connect to Jenkins succesfully}.
   
  # 7) Testing
  - Now, lets test to see that the GitHub Webhook is working perfectly well and connected to Jenkins for the resources to get deployed using this Jenkins Pipeline to the Console once its configuration code lands in the GitHub Repository.
  - So, go back to V.S Code and in the **Main.tf**, add the configuration or resource block of another resource like "gcs bucket.tf".
  - Now, in that project repository, get it inside there and run the git command to to push it to GitHub. So do
  - `git add .`
  - `git commmit -m "added gcs bucket configuration file"`
  - `git push`
  - Now, go to the Jenkins UI and see how the Pipeline automatically kicks-in without us doing anything.
 
  - Now, go to gcs and see those Buckets that has been created.
  - Then go to slack and see the new message there.

- END
- You can destroy by going bck to the Jenkinsfile and go to line `46 and line 51` and uncomment this section, if you want to destroy.
- Then you comment the "Aply" OR "Destroy" in line 41 to 45.   {It will destroy everything or all the created resources including the VM Itself.
  
















