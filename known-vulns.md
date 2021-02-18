## Attack #3 - Known Vulnerabilities

### Get the demo application
- Fork/Clone the example GitHub project
  - https://github.com/sonatype-nexus-community/sonatype-field-workshop/tree/main/struts2-rce-workshop

### Build and run the Docker image
- cd into the `struts2-rce-workshop` directory
- `mvn clean package` in project root
- `docker build -t hackme .`
- `docker run -d -p 9080:8080 hackme`
  - If 9080 is already used on your local machine, pick another port
- Once container comes online - verify by running in browser http://localhost:9080
- Run the exploit
  - `python2 exploit.py http://localhost:9080/orders/3 "whoami"`
   - `pwd` - where are we?
   - `whomai` - what user are we running this?
   - `ls -la` - what's in my directory?
   - `ls /` - what's my machine
   - `ls /etc` - what else we can find?
  
  - 2to3 -w exploit.py if you have python3

### Intro to OSS Index
- [Sonatype OSS Index](https://ossindex.sonatype.org/)
- [OSS Integrations](https://ossindex.sonatype.org/integrations)

### First Evaluation
- [`mvn org.sonatype.ossindex.maven:ossindex-maven-plugin:audit-aggregate -f pom.xml`](https://sonatype.github.io/ossindex-maven/maven-plugin/ )

### Sonatype Open Source Developer Tools
- [Visual Studio Code Extension](https://ossindex.sonatype.org/integration/vscode)
- [AHAB](https://ossindex.sonatype.org/integration/ahab)

### Sonatype Lift
- [Sonatype Lift for Azure DevOps](https://marketplace.visualstudio.com/items?itemName=SonatypeIntegrations.sonatype-lift-azure-extension)
