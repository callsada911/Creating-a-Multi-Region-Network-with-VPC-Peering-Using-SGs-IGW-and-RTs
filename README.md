# Creating-a-Multi-Region-Network-with-VPC-Peering-Using-SGs-IGW-and-RTs
Log in to the Terraform Controller Node EC2 Instance
Find the details for logging in to the Terraform Controller node provided by the hands-on lab interface and log in to the node using SSH:

ssh cloud_user@<IP-OF-TERRAFORM-CONTROLLER>
Note: This instance already has an EC2 instance profile (role) attached to it and has all necessary AWS API permissions required for this lab. It also has the AWS CLI set up and configured with the AWS account attached to this lab, for which the console login credentials are also provided in the lab interface page once the lab spins up.

After logging in, verify the version of Terraform installed (should be 12.29). Execute the following command to check:

terraform version
Clone the GitHub Repo for Terraform Code
Use the git command to clone the GitHub repo which has the Terraform code for deploying the solution of this lab. GitHub repo URL.

Execute the following command:

git clone https://github.com/linuxacademy/content-deploying-to-aws-ansible-terraform.git
Change to the directory for lab Terraform code:

cd content-deploying-to-aws-ansible-terraform/lab_network_vpc_peering
Examine the contents of the directory you're in:

ls
Deploy the Terraform Code
Initialize the Terraform directory you changed into to download the required provider

terraform init
Ensure Terraform code is formatted properly:

terraform fmt
Ensure code has proper syntax and no errors:

terraform validate
See the execution plan and note the number of resources that will be created:

terraform plan
Enter yes when prompted.

Deploy resources:

terraform apply
Enter yes when prompted.

After terraform apply has run successfully, you can use AWS CLI on the Controller node to list, describe created resources, and additionally also log in to the AWS Console to verify and investigate created resources.

Finally, on the Terraform Controller node CLI, delete all resources which were created and ensure that it runs through successfully.

terraform destroy
