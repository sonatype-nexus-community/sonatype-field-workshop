## Nexus Repository Manager

Quick Start - https://guides.sonatype.com/repo3/quick-start-guides/proxying-maven-and-npm/

# Installation Gotchyas
- If port 8081 already in use.  Start nexus `./bin/nexus run`

### Requirements

Before you can set up the proxy server for Maven and npm, you’ll need to install and configure the following external tools for the repository manager:

- Java 8 Development Kit (JDK) - Nexus Repository Manager is a Java server application. As explained in System Requirements, we strongly recommend using Java 8 to ensure effective runtime of Nexus Repository Manager 3.

- [Apache Maven](https://maven.apache.org/download.cgi) - When downloaded, Nexus Repository Manager 3 includes access to open source components from the Central Repository by default. These components are defined by both a settings.xml file and a Project Object Model file (POM), which maintains information on projects and dependencies.

- [npm](https://www.npmjs.com/get-npm) - A popular format supported by the repository manager. Unlike Maven, Nexus Repository Manager 3 doesn’t currently ship with a default npm repository configuration. These components are configured with an .npmrc file.
