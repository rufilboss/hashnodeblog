---
title: "Efficiently Managing Your Node.js Applications with NPM and PM2"
datePublished: Wed Mar 29 2023 07:02:37 GMT+0000 (Coordinated Universal Time)
cuid: clftcarfw000409mj4t1y7o7f
slug: efficiently-managing-your-nodejs-applications-with-npm-and-pm2
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1680623080123/51d777b1-bd4c-40e3-8d98-7c3270944a16.png
tags: nodejs, npm, monitoring, pm2, applications

---

**Node Package Manager (NPM)** and **Process Manager 2 (PM2)** are two popular tools used in managing Node.js applications. NPM is the default package manager for Node.js, while PM2 is a process manager designed to help manage Node.js applications in production. In this guide, we will explore the features of both NPM and PM2 and how to use them to manage your Node.js applications.

## What is NPM?

**Node Package Manager (NPM)** is a package manager for the Node.js platform. It is used to install, manage, and share packages and dependencies between Node.js applications. NPM is installed with Node.js by default and can be accessed from the command line interface.

One of the key features of NPM is the ability to install and manage dependencies for Node.js applications. Dependencies are external packages or libraries that are required by an application to function. NPM makes it easy to install, update, and remove these dependencies, as well as manage version compatibility between them.

Another important feature of NPM is the ability to publish and share packages with the wider Node.js community. Developers can use NPM to publish their packages and libraries and make them available to others for use in their applications. This makes it easier to build complex applications by leveraging existing code and functionality.

### How to use NPM

Using NPM is simple and straightforward. To get started, open a command prompt or terminal window and navigate to your Node.js application directory. From there, you can use NPM to install dependencies, update packages, and run scripts.

To install a dependency, use the following command:

```bash
npm install
#Install a package
npm install <package-name>
```

This will download and install the specified package, along with any dependencies required by the package.

To update a package, use the following command:

```bash
npm update <package-name>
```

This will update the specified package to the latest version, if available.

To run a script defined in your package.json file, use the following command:

```bash
npm run <script-name>
```

This will run the script with the specified name.

## What is PM2?

**Process Manager 2 (PM2)** is a process manager designed to help manage Node.js applications in production. PM2 provides features like process monitoring, automatic restarts, and load balancing to help ensure that Node.js applications are reliable and scalable.

One of the key features of PM2 is process monitoring. PM2 can monitor the performance and resource usage of Node.js processes, and alert you if there are any issues or errors. This can help you identify and resolve problems before they impact your application's performance or uptime.

Another important feature of PM2 is automatic restarts. If a Node.js process crashes or becomes unresponsive, PM2 can automatically restart it to ensure that your application stays online and available. This can help minimize downtime and ensure that your application is always accessible to users.

### How to use PM2

Using PM2 is also straightforward. To get started, you will need to install PM2 using NPM:

```bash
npm install pm2 -g
```

Once PM2 is installed, you can use it to manage your Node.js applications. To start an application using PM2, use the following command:

```bash
pm2 start <filename>
```

This will start the specified Node.js application as a PM2 process. PM2 will automatically monitor the process and restart it if it crashes or becomes unresponsive.

To view the status of your PM2 processes, use the following command:

```bash
pm2 status 
OR
pm2 list
```

This will show you the status of all running processes, including their resource usage

PM2 offers a range of commands for managing and monitoring processes, including `pm2 list` and `pm2 status`. Both commands provide useful information about running processes, but they have different purposes and outputs.

`pm2 list` is used to display a list of all running applications managed by PM2. The command displays the application name, its process ID (PID), and the status of the application (online, stopped, or errored). This command provides a quick overview of all the applications currently managed by PM2 and their current state.

On the other hand, `pm2 status` displays the status of a specific application managed by PM2. When you run this command followed by the application name or process ID, PM2 shows detailed information about the application, including its process ID, the path to the application file, CPU and memory usage, uptime, and logs. This command is useful when you want to check the details of a specific application and its current state.

In summary, `pm2 list` is useful for getting a quick overview of all applications managed by PM2, while `pm2 status` provides detailed information about a specific application. Both commands are important for monitoring and managing Node.js applications effectively.