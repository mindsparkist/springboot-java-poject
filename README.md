Installing the Java Development Kit (JDK) and Apache Maven on Ubuntu is a straightforward process thanks to Ubuntu's built-in package manager, `apt`. 

Here is the step-by-step process to get your environment set up.

### Step 1: Update Your Package Index
Before installing new software, it is always a good practice to update your local package list to ensure you get the latest versions and dependencies.
Open your terminal and run:
```bash
sudo apt update
```

### Step 2: Install the JDK
Ubuntu provides a package called `default-jdk` which automatically installs the latest stable, long-term support (LTS) version of OpenJDK for your specific Ubuntu release.

1. **Install the package:**
```bash
sudo apt install default-jdk
```
*(Press `Y` and `Enter` if prompted to confirm the installation).*

2. **Verify the installation:**
Once the installation finishes, check that Java is installed correctly by checking its version:
```bash
java -version
```
You should also check that the Java compiler (`javac`) is installed:
```bash
javac -version
```

### Step 3: Install Apache Maven
Maven is also available directly from the default Ubuntu repositories. 

1. **Install Maven:**
```bash
sudo apt install maven
```

2. **Verify the installation:**
Check that Maven was installed correctly and is recognizing your Java installation:
```bash
mvn -version
```
This command will output the Maven version, the Java version it is using, and the operating system details.

---

### Step 4: Set the `JAVA_HOME` Environment Variable (Recommended)
While many applications will find Java automatically, some build tools and IDEs require the `JAVA_HOME` environment variable to be set. 

1. **Find your Java installation path:**
Run the following command to see where Java is installed:
```bash
sudo update-alternatives --config java
```
You will see a path that looks something like `/usr/lib/jvm/java-11-openjdk-amd64/bin/java`. Copy the path **up to the `/jre/bin/java` or `/bin/java` part**. (e.g., just `/usr/lib/jvm/java-11-openjdk-amd64`).

2. **Open your environment file:**
You can add this to your `.bashrc` file (which we discussed earlier!) so it loads every time you open a terminal.
```bash
nano ~/.bashrc
```

3. **Add the variable:**
Scroll to the very bottom of the file and add these two lines, replacing the path with the one you copied in step 1:
```bash
export JAVA_HOME="/usr/lib/jvm/java-11-openjdk-amd64"
export PATH=$JAVA_HOME/bin:$PATH
```

4. **Save, exit, and apply:**
Save the file (`Ctrl+O`, `Enter`, `Ctrl+X` in Nano), and then apply the changes to your current session:
```bash
source ~/.bashrc
```
