## Attack #3 - Known Vulnerabilities

### Get the demo application
- Fork/Clone the example GitHub project
  - https://github.com/sonatype-nexus-community/sonatype-field-workshop/tree/main/struts2-rce-workshop

### Build and run the Docker image
- cd to `struts2-rce-workshop`
- `./mvnw clean package` in project root
- `docker build -t hackme .`
- `docker run -d -p 9080:8080 hackme`
  - If 9080 is already used on your local machine, pick another port
- Once container comes online - verify by running in browser http://localhost:9080
- Run the exploit
  - `python2 exploit.py http://localhost:9080/orders/3 "whoami"`
  - 2to3 -w exploit.py if you have python3

### Intro to OSS Index
- [Sonatype OSS Index](https://ossindex.sonatype.org/)
- [OSS Integrations](https://ossindex.sonatype.org/integrations)

### Sonatype Open Source Developer Tools
- [Visual Studio Code Extension](https://ossindex.sonatype.org/integration/vscode)
- [AHAB](https://ossindex.sonatype.org/integration/ahab)
