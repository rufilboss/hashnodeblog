---
title: "How to Install Jenkins on Ubuntu for Continuous Integration and Delivery"
datePublished: Tue Apr 25 2023 10:48:58 GMT+0000 (Coordinated Universal Time)
cuid: clgxkq0mo000509l730ej3x7z
slug: how-to-install-jenkins-on-ubuntu-for-continuous-integration-and-delivery
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1682493059765/7556b399-9e74-4cc0-b4bb-dd6ff8088fa2.png
tags: linux, devops, guide, jenkins, 2articles1week

---

In this blog, I'll provide a step-by-step guide on how to install Jenkins on an Ubuntu machine.

# What's Jenkins?

**Jenkins** is an open-source automation server that is widely used for continuous integration and continuous delivery. It is a powerful tool that can help teams automate their software development processes, from building and testing to deployment and delivery.

### **Step 1: Update Ubuntu**

Before installing Jenkins, it is recommended to update the Ubuntu machine to ensure that all the latest security updates and bug fixes are installed. To do this, open the terminal and run the following command:

```bash
sudo apt update
sudo apt upgrade
```

### **Step 2: Install Java**

Jenkins requires Java to run, so the next step is to install Java on your Ubuntu machine. To install Java, run the following command in the terminal:

```bash
sudo apt install openjdk-11-jdk
```

### **Step 3: Add Jenkins Repository**

To install Jenkins on Ubuntu, you need to add the Jenkins repository to your system. To do this, run the following commands in the terminal:

```bash
wget -q -O - https://pkg.jenkins.io/debian/jenkins.io.key | sudo apt-key add -
sudo sh -c 'echo deb http://pkg.jenkins.io/debian-stable binary/ > /etc/apt/sources.list.d/jenkins.list'
```

This will add the Jenkins repository to your system and enable you to install Jenkins.

### **Step 4: Install Jenkins**

Now that the Jenkins repository is added to your system, you can install Jenkins by running the following commands in the terminal:

```bash
sudo apt update
sudo apt install jenkins
```

This will install Jenkins on your Ubuntu machine.

### **Step 5: Start Jenkins**

Once Jenkins is installed, you can start the Jenkins service by running the following command in the terminal:

```bash
sudo systemctl start jenkins
```

You can also check the status of the Jenkins service by running the following command:

```bash
sudo systemctl status jenkins
```

### **Step 6: Access Jenkins Web Interface**

Now that Jenkins is installed and running, you can access the Jenkins web interface by navigating to [`http://localhost:8080`](http://localhost:8080) in your web browser.

You should see something like:

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1682508665675/7d5358e6-1962-4892-b645-6264bae22b63.png align="center")

You need to unlock it with the administrator password, so go back to your terminal and run this command:

```bash
sudo cat /var/lib/jenkins/secrets/initialAdminPassword
```

Once you have unlocked Jenkins, the Customize Jenkins page will appear, providing you with the opportunity to install a variety of useful plugins during your initial setup.

**You will be presented with two options:**

1. **Install suggested plugins**: this will install a set of plugins that are recommended based on the most common use cases.
    
2. **Select plugins to install**: this allows you to choose which set of plugins to install initially. By default, the suggested plugins will be selected when you first access the plugin selection page.
    

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1682508848748/35519ae1-ffc8-4a1f-98b2-e746c05f5e7d.png align="center")

After customizing Jenkins with plugins, the next step is for Jenkins to prompt you to create your initial administrator user.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1682509050015/00815946-f9a7-4e9b-9316-b2a55aa95dfd.png align="center")

Next to the instance configuration;

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1682509400510/fee4ac78-08db-405f-a617-be92698ce470.png align="center")

Click Save and Finish.

Boom🚀🚀🚀 we make it to the Jenkins dashboard.

# Conclusion

**Jenkins** is a powerful tool that can help teams automate their software development processes. By following these simple steps, you can install Jenkins on your Ubuntu machine and start using it to automate your software development processes.