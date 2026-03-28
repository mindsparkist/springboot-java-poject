To install the Java Development Kit (JDK) and Apache Maven on Ubuntu, you can use the APT package manager for the quickest setup. For developers who need the absolute latest versions, a manual binary installation is recommended. [1, 2, 3, 4] 
Method 1: Fast Installation (Using APT)
This is the easiest way to get started, though the versions in the official repositories may not always be the latest. [3, 5] 

   1. Update your package index:
   
   sudo apt update
   
   2. Install the JDK:
   You can install the [default-jdk](https://linuxize.com/post/how-to-install-apache-maven-on-ubuntu-20-04/) package, which currently points to OpenJDK 21 on Ubuntu 24.04 LTS.
   
   sudo apt install default-jdk
   
   3. Install Maven:
   
   sudo apt install maven
   
   4. Verify both installations:
   
   java -version
   mvn -version
   
   [6, 7, 8, 9, 10] 

------------------------------
Method 2: Latest Version (Manual Binary Install)
Use this method if you need a specific recent version, such as Maven 3.9.9. [1, 11] 
1. Install JDK
It is still recommended to use apt for the JDK to receive security updates. [7] 

sudo apt update
sudo apt install openjdk-17-jdk  # Or openjdk-21-jdk

2. Download and Extract Maven [12] 

   1. Download the archive: Get the latest link from the [Official Maven Download Page](https://maven.apache.org/download.cgi).
   
   wget https://dlcdn.apache.org/maven/maven-3/3.9.9/binaries/apache-maven-3.9.9-bin.tar.gz -P /tmp
   
   2. Extract to /opt:
   
   sudo tar xf /tmp/apache-maven-*.tar.gz -C /opt
   sudo ln -s /opt/apache-maven-3.9.9 /opt/maven  # Create a symbolic link for easy upgrades
   
   [13, 14, 15] 

3. Configure Environment Variables [1] 
You must tell Ubuntu where to find the new Maven binaries by editing your ~/.bashrc (for your user) or /etc/profile.d/maven.sh (system-wide). [1, 16] 

   1. Open the configuration file:
   
   sudo nano /etc/profile.d/maven.sh
   
   2. Add these lines (adjust paths if you used different versions):
   
   export JAVA_HOME=/usr/lib/jvm/default-java
   export M2_HOME=/opt/maven
   export PATH=${M2_HOME}/bin:${PATH}
   
   3. Apply changes:
   
   sudo chmod +x /etc/profile.d/maven.sh
   source /etc/profile.d/maven.sh
   
   [17, 18, 19, 20, 21] 

Summary of Key Commands

| Action [6, 14, 22, 23, 24] | APT Method | Binary Method |
|---|---|---|
| Install JDK | sudo apt install default-jdk | sudo apt install openjdk-17-jdk |
| Install Maven | sudo apt install maven | wget + tar to /opt/maven |
| Set Path | Automatic | Manual in ~/.bashrc or /etc/profile.d/ |
| Verify | mvn -version | mvn -version |

[23] [https://kedarpattanshetti.hashnode.dev](https://kedarpattanshetti.hashnode.dev/day-48-installing-jenkins-on-ubuntu)
[24] [https://sambitsinha.hashnode.dev](https://sambitsinha.hashnode.dev/day-1-cicd-setting-up-and-deploying-a-java-application)
