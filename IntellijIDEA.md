# Configure your IDE 
Set up your workspace environnement using JetBrains      
You should use Goland Jetbrains   

Download the package from   
https://www.jetbrains.com/idea/download/download-thanks.html?platform=windows

## Deployment
Go to Tools -> Deployment -> configuration 
Select SFTP, choose a name, and enter your remote IP Vm host and credentials
Press apply and save 
Select the tab Mappings and type /home/<user_name>/jenkins-pic 
Hit Save 
You can select Tools -> Start SSH Session... Select your remote machine

## Set Jenkins in your IDE 
Go to File -> Settings  -> Plugins 
and install Jenkins Control Plugin 
Restart IntellijIDEA
You got a right-hand side tab named Jenkins   
Click on the spanner to get the configuration dialog window
Fill Server Address, username, passwords, crumb data , jenkins version ver 2.x
Tick use green color....
![Jenkins_config](screenshots/jenkins_config_plugin.png)
### API token  
go to 
Copy in crumb data the API token previously saved in your notepad. 

## Remove CSRF failed check 
Go to Manage Jenkins -> Script console and run the following groovy script.
```groovy
import jenkins.model.Jenkins
def instance = Jenkins.instance
instance.setCrumbIssuer(null)
```
Result  

![Jenkins_screen](screenshots/jenkins_intellij_screen.png)
