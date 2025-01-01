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
- Then, go to your local or VS Code and clone it there by doing **git clone <paste the cloned URL here> and enter to clone it.

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



















