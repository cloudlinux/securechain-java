# Integration Guide

## Overview

This guide outlines the steps needed to integrate the TuxCare ELS Spring repository into your Java application. The repository provides trusted Java libraries that can be easily integrated into your Maven as well as Gradle project.

## Steps

### Step 1: Get user credntials
You need username and password in order to use TuxCare ELS Spring repository. Anonymous access is disabled. To receive username and password please contact sales@tuxcare.com
<!--
### Step 2: Locate the Repository

You can find the Trusted repository using the following link: [TuxCare ELS Spring repository](https://nexus-repo.corp.cloudlinux.com/#browse/browse:els_spring).-->

### Step 2: Create or Modify Your Build Tool Settings

#### Maven

If you are using Maven as your build automation tool, you will need to make changes in your `${MAVEN_HOME}/settings.xml` file. If the file does not already exist in your Maven home directory (`${MAVEN_HOME}`), you should create one. Open the `settings.xml` file with a text editor and include the following configuration:

```xml
<?xml version="1.0" encoding="UTF-8"?>
<settings xmlns="http://maven.apache.org/SETTINGS/1.1.0">
    <servers>
        <server>
     	    <id>repository-id</id>
     	    <username>${env.USERNAME}</username>
     	    <password>${env.PASSWORD}</password>
   	</server>
    </servers>
</settings>
```
Set your credentials via the following enviromnent variables:
```bash
export USERNAME=your-username
export PASSWORD=your-password
```
Here ```your-username``` and ```your-password``` are your credentials mentioned in the [Step 1](#step-1:-get-user-credntials).

You may choose an arbitrary allowed value instead of ```repository-id``` and use the same value in the following snippet from your `pom.xml` file:
```xml
<repositories>
    <repository>
        <id>repository-id</id>
        <url>https://nexus-repo.corp.cloudlinux.com/repository/els_spring/</url>
    </repository>
</repositories>
```
An example of maven project you can find 
[here](../examples/maven). Do not forget to set the enviromnet variables.
#### Gradle

If you are using Gradle as your build automation tool, make sure to include the following configuration in your project setup:

```gradle
repositories {
  maven {
    url = uri("https://nexus-repo.corp.cloudlinux.com/repository/els_spring")
    credentials {
            username = findProperty('USERNAME')
            password = findProperty('PASSWORD')
    }
  }
}
```
Set your credentials via the following enviromnent variables:
```bash
export ORG_GRADLE_PROJECT_USERNAME=your-username
export ORG_GRADLE_PROJECT_PASSWORD=your-password
```
Here ```your-username``` and ```your-password``` are your credentials mentioned in the Step 1.

An example of gradle project you can find 
[here](../examples/gradle). Do not forget to set the enviromnet variables.

## Verification

To confirm that the repository has been correctly established, include any library from the repository into your project and then run a build. The build tool you're using should be able to identify and resolve dependencies from the TuxCare ELS Spring repository.

## Conclusion

You've successfully integrated the TuxCare Vetted repository into your project. You can now benefit from the secure and vetted Java libraries it provides.
