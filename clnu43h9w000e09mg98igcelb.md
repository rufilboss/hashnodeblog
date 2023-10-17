---
title: "A beginner's guide to setting up AWS CLI with Terraform"
datePublished: Tue Oct 17 2023 09:18:25 GMT+0000 (Coordinated Universal Time)
cuid: clnu43h9w000e09mg98igcelb
slug: a-beginners-guide-to-setting-up-aws-cli-with-terraform
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1697534196750/a8814a7d-8284-4a11-96c3-b819c02e65d2.png
tags: aws, devops, terraform, iac, aws-cli

---

I recently acquired a new laptop and have been in the process of configuring my development environment. I believe it's important to share this process, as it might benefit newcomers preparing to set up their computers.

To start, I ensured that my Ubuntu machine was up to date by running the following commands:

```bash
sudo apt update
sudo apt upgrade
```

Once I had my system updated, I proceeded to install Terraform. I visited Terraform's official website and followed their installation instructions to get the latest version, which as of my last update in September 2023 is version 1.5.7.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1695505994305/f4165232-e402-442d-b920-76a4783e9f8f.png align="center")

So I ran the commands;

```bash
wget -O- https://apt.releases.hashicorp.com/gpg | sudo gpg --dearmor -o /usr/share/keyrings/hashicorp-archive-keyring.gpg
echo "deb [signed-by=/usr/share/keyrings/hashicorp-archive-keyring.gpg] https://apt.releases.hashicorp.com $(lsb_release -cs) main" | sudo tee /etc/apt/sources.list.d/hashicorp.list
sudo apt update && sudo apt install terraform
```

The provided code installs HashiCorp's Terraform on a Unix-like system:

1. It downloads HashiCorp's GPG key, converts it to text format, and stores it as `/usr/share/keyrings/hashicorp-archive-keyring.gpg`.
    
2. It adds a repository configuration for HashiCorp packages to the system's package sources, including the GPG key for package verification.
    
3. It updates the package lists and installs Terraform from the HashiCorp repository. This sequence ensures a secure and up-to-date Terraform installation on your system.
    

To verify the installation of Terraform run this command:

```bash
terraform --version
```

You should see a result similar to this if Terraform is successfully installed on your machine

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1695505467704/12aad3b4-4874-4706-896b-c3b7bdde9ad9.png align="center")

Now that we have Terraform installed, we can proceed to install AWS CLI and configure it so we can start using Terraform as our IAC tool for AWS.

If you don't have an AWS account, visit the [AWS](https://amazon.com) official website to create one.

Then, go to this [official doc](https://docs.aws.amazon.com/cli/latest/userguide/getting-started-install.html) and choose your OS to follow the installation guide.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1695761526178/4be6c4e6-9b95-4f39-8c09-60c41d3ee81d.png align="center")

After that, confirm your installation with;

```bash
aws --version
```

You should see something like this;

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1695938386084/4e2c8134-e369-46e5-860c-11ff82fb17d3.png align="center")

Now let's get our credentials from AWS, avoid using the root user of your account for this task; instead, employ an IAM user with precisely the required permissions. This is a recommended practice.

Upon logging into my account using this user, I located the necessary information for configuring Terraform to create the desired resources. Please familiarize yourself with where this information is stored in AWS, and consider securely storing it. If you download and retain the .csv file, ensure you know its location or can regenerate the data.

Take care of this file diligently, as unauthorized access could result in unauthorized resource provisioning and substantial charges to your account. It's essential to have a billing alert in place; if you haven't already, please set one up without any delay. There should be no excuses for not having this safeguard in place.

Executing it should yield the following outcome once the configuration is completed.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1696668193966/678202c4-960b-44b9-bfff-e306b2e7736e.png align="center")

Now let's create AWS S3 to test if it's working perfectly;

After writing the shortcode to create an S3 bucket I ran the `terraform plan` command to show us the plan for the resources to be created

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1697532616865/8db01ad4-c7a6-4658-a552-54ebc89c8676.png align="center")

Then let's run `terraform apply` to create the resource, you can add ***\--auto-approve*** to it or manually approve it by ***yes.***

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1697532930023/b8b04f04-d0bd-4bfd-90c5-91eaa28dbdc4.png align="center")

After approving the resource creation with **yes**, you can see that our resources now carry **creating...** status

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1697533033052/7d14229d-3aae-41bb-8aea-d104a5c49c0e.png align="center")

Now that we've our AWS S3 created, let's confirm on the AWS Console

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1697533104919/c07afbef-92cd-4478-ba25-bda7ba5aefee.png align="center")

Boom our S3 bucket is created successfully. Now, let's destroy it again using our terraform command; `terraform destroy` with ***\--auto-approve*** or input ***yes.***

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1697533345309/3f3759ac-124b-4e32-80b2-53f9d91bbd49.png align="center")

I choose to use yes instead

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1697533403389/e4c77d20-6731-436c-8b93-be5a05ee60e4.png align="center")

That's it for this guide you can drop your question in the comment section if you have any questions, Thanks