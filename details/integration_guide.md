# Integration Guide

## Overview

This guide outlines the steps needed to integrate the TuxCare Vetted repository into your Java application. The repository provides trusted, vetted Java libraries that can be easily integrated into your Maven project.

## Steps

### Step 1: Locate the Repository

You can find the Trusted repository using the following link: [TuxCare Vetted Repository](https://nexus-repo.corp.cloudlinux.com/#browse/browse:tuxcare_vetted).

### Step 2: Create or Modify Your Build Tool Settings

If you are using Maven as your build automation tool, you will need to make changes in your `${MAVEN_HOME}/settings.xml` file. If the file does not already exist in your Maven home directory (`${MAVEN_HOME}`), you should create one. Open the `settings.xml` file with a text editor and include the following configuration:

```xml
<?xml version="1.0" encoding="UTF-8"?>
<settings xmlns="http://maven.apache.org/SETTINGS/1.1.0">
    <profiles>
        <profile>
            <id>tuxcare</id>
            <repositories>
                <repository>
                    <id>tuxcare-vetted</id>
                    <name>TuxCare Vetted Repository</name>
                    <url>https://nexus-repo.corp.cloudlinux.com/repository/tuxcare-vetted/</url>
                </repository>
            </repositories>
        </profile>
    </profiles>
    <activeProfiles>
        <activeProfile>tuxcare</activeProfile>
    </activeProfiles>
</settings>
```

In this configuration, a profile named `tuxcare` is created. The TuxCare Vetted repository is added to this profile, and this profile is set to be activated by default in the `activeProfiles` section.

If you are using Gradle as your build automation tool, make sure to include the following configuration in your project setup:

```gradle
repositories {
  maven {
    url = uri("https://nexus-repo.corp.cloudlinux.com/repository/tuxcare-vetted/")
  }
}
```

## Verification

To confirm that the repository has been correctly established, include any library from the repository into your project and then run a build. The build tool you're using should be able to identify and resolve dependencies from the TuxCare Vetted repository.

## Conclusion

You've successfully integrated the TuxCare Vetted repository into your project. You can now benefit from the secure and vetted Java libraries it provides.
