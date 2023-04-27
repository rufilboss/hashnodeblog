---
title: "Getting Started with Apache Tomcat on Linux: A Beginner's Tutorial"
datePublished: Thu Apr 27 2023 08:27:20 GMT+0000 (Coordinated Universal Time)
cuid: clgyv3f1c000409jma0wb3df2
slug: getting-started-with-apache-tomcat-on-linux-a-beginners-tutorial
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1682583917298/c70c3d53-f478-4e6b-9901-b8e5e33b3a63.png
tags: linux, devops, tomcat, 2articles1week, linux-server

---

In this blog post, I'll guide you through the process of installing and setting up Apache Tomcat on a Linux server.

# What's Apache Tomcat?

**Apache Tomcat** is an open-source web server and servlet container that is widely used for hosting Java-based web applications.

## **Step 1**

**Prerequisites:** Before we start installing Apache Tomcat, make sure your Linux server meets the following requirements:

* Java Development Kit (JDK) version 8 or later is installed on the server
    
* A user account with `sudo` privilege is required to install and configure Apache Tomcat
    
* The server has a static IP address assigned
    

## **Step 2**

**Download Apache Tomcat:** To download the latest version of Apache Tomcat, go to the official Apache Tomcat website and download the binary distribution package. Once the download is complete, extract the package to a directory of your choice using the following command:

```bash
sudo tar -zxvf apache-tomcat-<version>.tar.gz -C /opt/
```

Replace `<version>` with the version number of the package you downloaded.

## **Step 3**

**Configure Environment Variables:** Next, we need to set up the environment variables for Apache Tomcat. Open the `/etc/environment` file using your preferred text editor and add the following lines:

```bash
export JAVA_HOME=/usr/lib/jvm/java-<version>-openjdk-amd64
export CATALINA_HOME=/opt/apache-tomcat-<version>
export PATH=$PATH:$CATALINA_HOME/bin
```

Replace `<version>` with the version number of the Java Development Kit and Apache Tomcat that you installed.

Save the changes and exit the text editor.

## Step 4

**Start Apache Tomcat:** To start Apache Tomcat, run the following command:

```bash
sudo /opt/apache-tomcat-<version>/bin/startup.sh
or
sudo systectl  start tomcat
```

Replace `<version>` with the version number of Apache Tomcat that you installed.

You should see the following output indicating that Apache Tomcat has started successfully:

```bash
Using CATALINA_BASE:   /opt/apache-tomcat-<version>
Using CATALINA_HOME:   /opt/apache-tomcat-<version>
Using CATALINA_TMPDIR: /opt/apache-tomcat-<version>/temp
Using JRE_HOME:        /usr/lib/jvm/java-<version>-openjdk-amd64
Using CLASSPATH:       /opt/apache-tomcat-<version>/bin/bootstrap.jar:/opt/apache-tomcat-<version>/bin/tomcat-juli.jar
Tomcat started.
```

## Step 5

**Verify Apache Tomcat Installation:** To verify that Apache Tomcat is installed correctly, open your web browser and go to `http://<server_ip>:8080`. You should see the Apache Tomcat welcome page.

## Step 6

**Configure Apache Tomcat:** To configure Apache Tomcat, open the `server.xml` file located in the `conf` directory of the Apache Tomcat installation directory. You can use your preferred text editor to make the changes.

Some of the common configuration changes that you might want to make include setting the port number, configuring SSL, and changing the default web application.

## Step 7

**Stop Apache:** Tomcat To stop Apache Tomcat, run the following command:

```bash
sudo /opt/apache-tomcat-<version>/bin/shutdown.sh
or
sudo systemctl stop tomcat
```

Replace `<version>` with the version number of Apache Tomcat that you installed.

If Jenkins or any other useful service is using the port currently used by Apache Tomcat, you will need to change the port that Apache Tomcat uses.

**Here are the steps to do this:**

1. Stop the Apache Tomcat server by running the following command:
    

```bash
sudo systemctl stop tomcat
```

1. Open the `server.xml` file located in the conf folder of your Apache Tomcat installation. You can use any text editor to do this. For example, if your Apache Tomcat installation is located in the `/opt/tomcat` directory, you can run the following command:
    

```bash
sudo nano /opt/tomcat/conf/server.xml
```

1. Find the following line in the server.xml file:
    

```bash
<Connector port="8080" protocol="HTTP/1.1"
           connectionTimeout="20000"
           redirectPort="8443" />
```

1. Change the port number `8080` to a different port number that is not being used by any other application. For example, you can change it to `8081`.
    

```bash
<Connector port="8081" protocol="HTTP/1.1"
           connectionTimeout="20000"
           redirectPort="8443" />
```

1. Save the `server.xml` file and exit the text editor.
    
2. Start the Apache Tomcat server by running the following command:
    

```bash
sudo systemctl start tomcat
```

**Apache Tomcat** should now be running on the new port number that you specified. You can access the Apache Tomcat web interface by entering the new port number in your web browser. For example, if you changed the port number to `8081`, you can access the Apache Tomcat web interface by entering the following URL in your web browser:

```bash
http://<your-server-ip>:8081/
```

**NOTE:** You'll also need to update the port number in any configuration files or scripts that reference the Apache Tomcat port number.

# Conclusion

In this blog post, I've walked you through the process of installing and setting up Apache Tomcat on a Linux server. Apache Tomcat is a powerful and versatile web server that can be used to host Java-based web applications. With these steps, you can easily get started with Apache Tomcat on your own Linux server.