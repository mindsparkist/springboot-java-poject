To install JDK and Maven on Ubuntu, the recommended approach is to use the  package manager for simplicity and ease of updates. [1]  
1. Install JDK (Java Development Kit) [2]  
Maven requires a JDK to be installed. OpenJDK 17 is a recommended, stable, Long-Term Support (LTS) version. 

• Update your package lists: 
• Install OpenJDK 17: 
• Verify the installation: 
• You should see output indicating OpenJDK version 17. 
• Set the  environment variable (optional but recommended for clarity):While Maven often finds the JDK automatically, setting  explicitly is a best practice. The path for APT-based OpenJDK 17 is typically . 

	• Open your  (or ) file in a text editor (e.g., ): 
	• Add the following line to the end of the file: 
	• Save the file (Ctrl+O, Enter) and exit the editor (Ctrl+X). 
	• Apply the changes to your current terminal session: [3, 4, 5, 6, 7]  

2. Install Maven 
You can install Maven using the  package manager or by manually downloading the binary archive for the latest version. [8, 9, 10]  
Method A: Install via APT (Recommended for simplicity) This method is the simplest but might not provide the absolute latest Maven version. 

• Install Maven: [12]  

Method B: Install Manually (For the latest version) This method ensures you get the most up-to-date release directly from the Apache Maven website. 

• Download the latest Maven binary archive:First, check the  Apache Maven website 
 for the latest version (e.g., 3.9.9 as of a recent snippet). 
• Extract the archive: 
• Create a symbolic link for easy version management: 
• Configure environment variables: 

	• Create a script file in  to set  and update the  for all users: 
	• Add the following lines to the file: 
	• Save and exit the editor. 
	• Make the script executable: 
	• Apply the changes: [3, 13, 14, 15, 16]  

3. Verify Maven Installation 
Open a new terminal session (or run  if you only edited that file, or  as needed) and verify the installation: [17, 18, 19, 20]  
The output should display the Maven version, along with the installed Java version and  path, confirming a successful setup. [3]  
