# Ways To Install Jenkins on Windows & Linux
## --- INSTALL JENKINS ON LINUX METHOD -1 ---

1. Update the package index:
   ```bash
   sudo apt update -y
   ```

2. Install OpenJDK 11:
   ```bash
   sudo apt install openjdk-11-jre -y
   ```

3. Add Jenkins repository key:
   ```bash
   curl -fsSL https://pkg.jenkins.io/debian-stable/jenkins.io-2023.key | sudo tee /usr/share/keyrings/jenkins-keyring.asc >/dev/null
   ```

4. Add Jenkins repository to sources:
   ```bash
   echo "deb [signed-by=/usr/share/keyrings/jenkins-keyring.asc] https://pkg.jenkins.io/debian-stable binary/" | sudo tee /etc/apt/sources.list.d/jenkins.list >/dev/null
   ```

5. Update the package index again:
   ```bash
   sudo apt-get update -y
   ```

6. Install Jenkins:
   ```bash
   sudo apt-get install jenkins -y
   ```

7. Enable and start Jenkins service:
   ```bash
   sudo systemctl enable jenkins
   sudo systemctl start jenkins
   ```

8. Check the status of Jenkins:
   ```bash
   sudo systemctl status jenkins
   ```

You've successfully installed Jenkins on your Ubuntu machine. Use the provided commands to set up Jenkins for your continuous integration and automation needs.
```

## --- INSTALL JENKINS ON LINUX METHOD -2 ---

1. Update the package index:
   ```bash
   sudo apt update -y
   ```

2. Install OpenJDK 11:
   ```bash
   sudo apt install openjdk-11-jre -y
   ```

3. Download the Jenkins WAR file:
   ```bash
   sudo wget https://updates.jenkins.io/download/war/2.387.3/jenkins.war
   ```

4. Start Jenkins with a specific port (e.g., 8082):
   ```bash
   java -jar jenkins.war --httpPort=8082
   ```

Once Jenkins is running, you can access the Jenkins web interface by opening a web browser and navigating to `http://your_server_ip:8082`.


## --- INSTALL JENKINS ON WINDOWS ---

### Follow these step-by-step instructions to install Jenkins on your Windows machine:

1. Visit the official [Jenkins website](https://www.jenkins.io/) and navigate to the "Download" section.
2. Click on the "Windows" tab and download the latest stable release of Jenkins for Windows as a "Generic Java package (.war)" file.
3. Once the download is complete, locate the Jenkins ".war" file.
4. Press "Win + R" to open the Run dialog, type "cmd", and hit Enter to open a command prompt.
5. Use the `cd` command to navigate to the directory where you saved the Jenkins ".war" file. For example, if it's in the "Downloads" folder, use: `cd C:\Users\YourUsername\Downloads`.
6. In the command prompt, start Jenkins by running: `java -jar jenkins.war`.
7. Jenkins will initialize, and you'll see log output in the command prompt.
8. Open a web browser and go to [http://localhost:8080/](http://localhost:8080/), the default URL for the Jenkins web interface.
9. On the Jenkins web page, you'll be prompted to enter the initial administrator password. To get the password, go back to the command prompt where Jenkins is running and find the line that says "Please unlock Jenkins". Copy the alphanumeric password.
10. Paste the administrator password into the Jenkins web interface and click "Continue".
11. On the next screen, select "Install suggested plugins" to install the recommended set of plugins for basic Jenkins functionality.
12. Wait for the plugin installation to complete. Once done, you'll be asked to create an admin user. Provide the required details and click "Save and Continue".
13. You'll now be presented with the Jenkins dashboard, where you can start configuring your projects and automation workflows.

Congratulations! You've successfully installed Jenkins on your Windows machine. Explore the wide range of features and capabilities Jenkins offers for continuous integration and delivery.
