# Ways To Install Jenkins on Windows & Linux
## --- INSTALL JENKINS ON LINUX METHOD -1 ---
sudo apt update -y
sudo apt install openjdk-11-jre -y
curl -fsSL https://pkg.jenkins.io/debian-stable/jenkins.io-2023.key |sudo tee \
  /usr/share/keyrings/jenkins-keyring.asc >/dev/null
echodeb [signed-by=/usr/share/keyrings/jenkins-keyring.asc] \
  https://pkg.jenkins.io/debian-stable binary/ |sudo tee \
  /etc/apt/sources.list.d/jenkins.list >/dev/null
sudo apt-get update -y 
sudo apt-get install jenkins -y
sudo systemctl enablejenkins
sudo systemctl start jenkins
sudo systemctl status jenkins
## --- INSTALL JENKINS ON LINUX METHOD -2 ---
sudo apt update -y
sudo apt install openjdk-11-jre -y
sudo wget https://updates.jenkins.io/download/war/2.387.3/jenkins.war
java -jar Jenkins.war  --httpPort=8082
## --- INSTALL JENKINS ON WINDOWS ---
Follow these step-by-step instructions to install Jenkins on your Windows machine:
	1. Visit the official Jenkins website at  https://www.jenkins.io/ and go to the "Download" section.
	2. Click on the "Windows" tab and download the latest stable release of Jenkins for Windows as a "Generic Java package (.war)" file.
	3. Once the download is finished, navigate to the location where you saved the Jenkins ".war" file.
	4. Open a command prompt by pressing "Win + R" and typing "cmd", then hit Enter.
	5. In the command prompt, navigate to the directory where you saved the Jenkins ".war" file using the cd command. For example, if you saved the file in the "Downloads" folder, you would use the command: cd C:\Users\YourUsername\Downloads.
	6. Once you're in the correct directory, run the following command to start Jenkins: java -jar jenkins.war.
	7. Jenkins will start initializing, and you'll see some log output in the command prompt.
	8. Open a web browser and go to  http://localhost:8080/. This is the default URL for accessing the Jenkins web interface.
	9. On the Jenkins web page, you'll be prompted to enter the initial administrator password. To obtain the password, go back to the command prompt where Jenkins is running and look for the line that says "Please unlock Jenkins". Copy the alphanumeric password from there.
	10. Paste the administrator password into the Jenkins web interface and click "Continue".
	11. On the next screen, choose the option "Install suggested plugins" to install the recommended set of plugins. This will enable basic functionality in Jenkins.
	12. Wait for the plugin installation to complete. Once done, you'll be prompted to create an admin user. Fill in the required details and click "Save and Continue".
	13. Finally, you'll see the Jenkins dashboard, where you can start setting up your projects and automation workflows.
That's it! You have successfully installed Jenkins on your Windows machine. Feel free to explore the various features and capabilities offered by Jenkins for continuous integration and delivery.
![image](https://github.com/EmAdd9/Jenkins-Day03/assets/91713238/1f84f3ce-3934-471b-9f53-2373f3f6408e)
