Terraform


What is Terraform?

Terraform is an infrastructure as code tool that lets you build, change, and version cloud and on-premesis resources safely and efficiently. We can make things In the cloud, get information from the cloud, manage and edit things.


Terraform creates and manages resources on cloud platforms and other services through their application programming interfaces (APIs). Providers enable Terraform to work with virtually any platform or service with an accessible API. It's universal for majority platforms. 


Terraform Installation:

Does not inclube Ubuntu or RHEL/Centos Systems

For Mac Users

Install Homebrew, a free open source package management system for macOS.-> this will allow you to install terraform.

  Type: $brew tap hashicorp/tap and press ENTER

For Windows Users

Install Chocolatey, a free open source package management system for windows.-> this will allow you to install terraform.

Now install terraform from your command line -> Bash (windows) or Zsh (macOS/linux)

  Type: $brew install hashicorp/tap/terraform and press ENTER



Terraform Installation Varification:

Verify that the installation worked by opening a new terminal session and listing Terraform's available subcommands.

  Type: terraform and then press ENTER-> All terraform commands with meanings will appear.

If you use either Bash or Zsh as your command line shell, you can enable tab completion for Terraform commands. To enable autocomplete, first ensure that a configuration file exists for your chosen shell.

  Type: touch ~/.bashrc press ENTER
or
  Type: touch ~/.zshrc press ENTER

Then install the autocomplete package.

  Type: terraform -install-autocomplete press ENTER

RESTART SHELL TO ENABLE

Checking Terraform version: in Shell Type: terraform -version

Something similar to this should appear:
terraform -version
Terraform v1.12.0


TERRAFORM AND AWS CONFIGURATION 

Using Terminal or Bash Command Line

1. Create a new directory for the Terraform configuration

  Type: mkdir terraform.tf press Enter (folder for new working project)

2. Change into the directory.

  Type: cd terraform.tf press ENTER (going into folder)

3. Create Authentication file (if you do not make terraform file, then youn can not do anything in terraform)

  Type: touch 0-auth.tf press ENTER
  Type: touch main.tf press ENTER
  Type: Cat 0-auth.tf press ENTER (this will check and show that file is empty)

  The 0 is the number file. Auth is Authenticating to AWS. So you need to make a file to Authenticate.

  TERRAFORM STARTS FROM A FILE AND FOLDER LEVEL!!!!!!

4. Switching to Virtual Studio Code known as VS Code
  
  Type: code . press ENTER (this will open up VS Code allowing you to create infrastructure, edit and manage)

5. Click Terminal and select new Terminal. Select Zsh or Bash as default Terminal.

6. Copy and paste script to 0-auth.tf file (if script available) 

  provider "aws" {
  region = "eu-west-1"
}

terraform {
  required_providers {
    aws = {
      source  = "hashicorp/aws"
      version = "~> 3.0"
    }
  }
}

7. File and Save. Region in AWS and Terraform should match.

8. Go into AWS and look at your default region.

Run Terraform I(V)PAD commands:

  1. terraform init: Prepare your working directory for other commands
  2. terraform validate: Check whether the configuration is valid
  3. terraform planShow: Changes required by the current configuration
  4. terraform apply: Create or update infrastructure
  5. terraform destroy: Destroy previously-created infrastructure

9. Run pwd (print working directory)
10. cd .. (change directory up one level up) to terraform folder
11. ls -a (shows list of hidden files inside of folder)
12. cp .gitignore folder/ (this copies .gitignore file into folder name of choice)(we need this gitignore file for security to make sure files are not replicated into the cloud)

If you created an EC2, VPC, Security Group, etc., you would log into AWS to see if it the resource is connected and running. # wk6_assignment
# wk6_assignment
# wk6_github
