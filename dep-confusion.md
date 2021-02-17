# Attack #1 - Namespace Confusion 
(Dependency Confusiuon)

<img src="https://github.com/sonatype-nexus-community/sonatype-field-workshop/blob/main/images/dep_confusion.png" width="600">

## Exercises
- Configure our Repo to demonstrate the attack
  - Confirm npmjs proxy repo
  - Create npm hosted repo
  - Upload to hosted
        - [cupitt-aviation-weather-0.47.tgz](https://github.com/sonatype-nexus-community/sonatype-field-workshop/blob/main/deps/cupitt-aviation-weather-0.47.tgz)
  - Don't put them in a group yet
  - Create sample app; mkdir; npm init; npm --save i cupitt-aviation-weather
  - Look at group order
  
- [Routing Rules](https://help.sonatype.com/repomanager3/repository-management/routing-rules)



## Setup Gotchyas:
- Make Routing rule: `^/cupitt-aviation-weather/.*`
- `npm config set registry http://localhost:8081/repository/npm-group` before installing cupitt-aviation-weather
- npm install cupitt-aviation-weather



## Sonatype Materials:
- Brian Fox on what this means: https://blog.sonatype.com/why-namespacing-matters-in-public-open-source-repositories
- Using NXRM Routing rules to minimise risk: https://blog.sonatype.com/namespace-confusion-minimizing-risk-with-nexus-repository
- Latest update on copycats: https://blog.sonatype.com/sonatype-spots-150-malicious-npm-packages-copying-recent-software-supply-chain-attacks
- Original Blog: https://blog.sonatype.com/dependency-hijacking-software-supply-chain-attack-hits-more-than-35-organizations
- Community Script to check repo: https://github.com/sonatype-nexus-community/repo-diff

## Outside Coverage
- https://medium.com/@alex.birsan/dependency-confusion-4a5d60fec610
- https://www.bleepingcomputer.com/news/security/researcher-hacks-over-35-tech-firms-in-novel-supply-chain-attack/ 
- https://gizmodo.com/love-on-yourself-with-lelos-valentines-day-sale-1846220377
- https://www.theregister.com/2021/02/10/library_dependencies_attack/
- https://www.businessinsider.com/supply-chain-hacker-alex-birsan-apple-microsoft-neftlix-2021-2
- https://thestack.technology/security-researcher-hacks-apple-google-microsoft/
- https://informationsecuritybuzz.com/expert-comments/microsoft-uber-and-tesla-amongst-tech-companies-vulnerable-to-new-automated-supply-chain-attack-expert-insight/
