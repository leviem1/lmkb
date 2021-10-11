# OpenJDK and Oracle JDK Licensing

After Java 8, and again as of Java 17, Oracle changed the license in which it distributes its 
Java Development Kit (JDK). Oracle has also been supporting the OpenJDK project for years, which
is distributed under a more permissive open source license. Here are the primary differences 
between these distributions at the time of writing.

| | OpenJDK | Oracle JDK (older than 17) | Oracle JDK (17 and newer) |
| --- | --- | --- | --- |
| Free for personal use? | Yes | Yes | Yes |
| Free for development use? | Yes | Yes | Yes |
| Free for commercial use? | Yes | **No** | Yes* |
| Available at: | <https://jdk.java.net/> | <https://www.oracle.com/java/technologies/javase-downloads.html> | <https://www.oracle.com/java/technologies/javase-downloads.html> |
| License | [GNU GPLv2, w/ Classpath Exception](https://openjdk.java.net/legal/gplv2+ce.html) | [OTN](https://www.oracle.com/downloads/licenses/javase-license1.html) | [NFTC](https://www.oracle.com/downloads/licenses/no-fee-license.html)* |

\* The NFTC license is a free-to-use license valid for a full year after the next LTS release.

***This information is for reference only. Please contact Oracle for more information.***

## Alternatives
There are many vendors in addition to Oracle that distribute their own implementation of the
OpenJDK. Support and production-readiness vary between vendors.

Some honorable mentions include:
- [Amazon Corretto](https://aws.amazon.com/corretto/)
- [Azul Zulu](https://www.azul.com/downloads/?package=jdk#download-openjdk)
