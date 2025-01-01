# Terraform-Jenkins-CICD-Pipeline-Project

# DEPLOYING INFRASTRUCTURE USING THE CI/CD JENKINS PIPELINE


- Best practices actually says that we should avoid deploying infrastructure locally or manually using those terraform commands like `terraform init`, `terraform plan`, `terraform apply` and `terraform destroy`.
- So, Best practices wants us to make use of **Automation** to deploy infrastructure. Meaning that we should make use of an **Automation Pipeline** to deploy infrastructure. Therefore, we would make use of the Jenkins Pipeline process to deploy our infrastructure in an Automated way or process using the **Pipeline Script**
- Note that, we have Cloud Build within Google Cloud that we can use to also automate the pipeline just like Jenkins. Any CI tool can be used here like **Bamboo**, etc
  <img width="1148" alt="Screenshot 2025-01-01 at 10 54 10 AM" src="https://github.com/user-attachments/assets/2cae4a88-9a2a-424c-8a11-e01aba6e2b41" />

# IMPLEMENTATION
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
