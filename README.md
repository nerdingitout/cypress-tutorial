# Deploy your first e2e Cypress test on Red Hat Openshift

## Introduction

This tutorial aims to demonstrate the e2e tests using cypress tool.
<br>The following Architecture diagram gives an overview of how Cypress is different from Selenium.
<img width="1194" alt="Screenshot 2021-02-02 at 11 54 31" src="https://user-images.githubusercontent.com/78303150/106593877-a2062480-6551-11eb-8732-7951c157f9e8.png">

## Prerequisites

For this tutorial you will need:

- Your own GitHub account
- Sign up for your IBM Cloud account – https://ibm.biz/BdfELM
- Red Hat OpenShift Cluster 4 on IBM Cloud. You can get it from
  - URL: https://oc-jenkins.mybluemix.net/
  - Key: oslab
- oc CLI (can be downloaded from this link or you can use it at http://shell.cloud.ibm.com/.
- Node.js: https://nodejs.org/en/download/
- Visual Studio Code: https://code.visualstudio.com/download
- Register for the live stream and access the replay – https://www.crowdcast.io/e/testing-with-cypress/


## Estimated Time

It will take you around 15 minutes to complete this tutorial.

## Steps

- Fork the GitHub repo
- Install dependencies by running the following command in terminal (from inside your app directory i.e. where package.json is located): <I><B>npm install </I></B>
- Login to OpenShift Cluster from the CLI & Create Project
- Install Jenkins Operator from OperatorHub
- Access Jenkins 
## Fork and Clone the GitHub repo

- First thing you need to do is fork the GitHub repository to your own GitHub account so you can make your own changes later.
- Clone your fork of the repository.<br>

```
git clone https://github.com/<YOUR-ACCOUNT-NAME>/cypress-tutorial
```
## Login to OpenShift Cluster from the CLI & Create Project
- Go to the web console and click on your username at the top right then 'Copy Login Command', then display the token and copy the ```oc login``` command in your terminal.

![login](https://user-images.githubusercontent.com/36239840/97104809-26821500-16d0-11eb-936e-c2b7fb914523.JPG)
- Create ```cypress-project``` project.
```
oc new-project cypress-project
```
## Install Jenkins Operator from OperatorHub
- From the Administrator perspective, go to OperatorHub, search for 'Jenkins Operator' and click on install.
![image](https://user-images.githubusercontent.com/36239840/107520994-74f9e780-6bcb-11eb-8859-33e4a5258672.png)
- You will be redirected to Operator Installation page. Make sure that you are installing it on the same namespace you are working in, as for approval strategy you can go with Automatic.
![image](https://user-images.githubusercontent.com/36239840/107521118-9a86f100-6bcb-11eb-88e0-9dea6ecbaf27.png)
- Go to Installed Operators, and click on Jenkins Operator.
![image](https://user-images.githubusercontent.com/36239840/107522810-817f3f80-6bcd-11eb-8da7-92015613f505.png)
- Notice that Jenkins Operator provides several APIs that you can use in your project. Create an instance of 'Jenkins'.
![image](https://user-images.githubusercontent.com/36239840/107522948-a96ea300-6bcd-11eb-8f75-0505ccd08375.png)
- You will be redirected to Create Jenkins page, You can keep the default values for now.
![image](https://user-images.githubusercontent.com/36239840/107523302-05392c00-6bce-11eb-90eb-ce9ca13106b2.png)
## Access Jenkins
- Creating the pod will take few minutes, once done you will see that the pod is in ready state and colored in dark blue. To access Jenkins, simply click on the arrow at the top corner of the pod.
![image](https://user-images.githubusercontent.com/36239840/107650481-f74fdd80-6c97-11eb-92ab-5bf13a0e27cb.png)
- You will be redirected to the application that's shown as follows. CLick on Login with OpenShift and authorize access to your account so you can use Jenkins.
![image](https://user-images.githubusercontent.com/36239840/107650596-1a7a8d00-6c98-11eb-8cf4-7d027d8efd8c.png)
- Once you login to Jenkins, you will be redirected to the homepage that looks like the following. In the next steps, you will be using Jenkins to demonstrate end to end testing.
![image](https://user-images.githubusercontent.com/36239840/107651735-49ddc980-6c99-11eb-9283-e7c08540f4d2.png)
## Manage Jenkins and install packages
- For this tutorial, you will need to install several packages. To do that, first go to 'Manage Jenkins' from the navigation menu shown at the left.
![manage](https://user-images.githubusercontent.com/36239840/107872100-1da49180-6ec1-11eb-88a6-4316a80e38f9.JPG)
- Scroll all the way down to 'System Configuration' and select 'Manage Plugins'
![system plugin](https://user-images.githubusercontent.com/36239840/107872130-5e040f80-6ec1-11eb-9be0-13d84b46eb6a.JPG)
- In the filter textbox, search for 'NodeJs' and 'Xvfb' to install these plugins.\
![image](https://user-images.githubusercontent.com/36239840/107872345-2e560700-6ec3-11eb-8e25-89f8fb5a9278.png)
![image](https://user-images.githubusercontent.com/36239840/107872375-60ffff80-6ec3-11eb-9c30-e0d649978ffb.png)


## Summary

In this tutorial, you created your first test with cypress and run them on Openshift Cluster.
