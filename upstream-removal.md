## Attack #2 - Removal of Upstream Sources

#### [Migrating Away From JCenter](https://jeroenmols.com/blog/2021/02/04/migratingjcenter/)
This week JFrog - out of nowhere - announced to completely remove their Maven repository. Since they’ll pull it offline already by May 2021 (!!!) it’s time to urgently migrate away. This blogpost will guide how to get started.

[The Central Repository Stands to Support Sailors from Bintray - 3 steps to take now to protect your builds from failing]
(https://blog.sonatype.com/the-central-repository-stands-to-support-sailors-from-bintray-how-to-migrate)

## 1. Set up a Proxy Repository to Cache Your Components
We will use Nexus Repository Manager 3 to proxy OSS component repositories.
- https://jcenter.bintray.com/

## 2. Test Availability & Raise Migration Tickets
Once you have connectivity set up, you should test your builds without JCenter availability by temporarily removing it from the group, This will help you to identify what components you have that are currently JCenter exclusives - and what you’ll need keep cached.

## 3. Finalize Migration
Once all the artifacts you need have migrated over to Central and your build clears, you are sailing in smooth waters once again. With Repository in place your experience should be close to seamless. You can now finalize your transition and enjoy calm weather once more.

<br>
...Continue to Lab 4 by clicking: https://github.com/sonatype-nexus-community/sonatype-field-workshop/blob/main/known-vulns.md
