<h1>Installing Jenkins</h1>

First create an aws ec2 instance and login to the instance

Update the ubuntu instance
```bash
<a>sudo apt-get update</a>
```

Jenkins is a java based software so first you want to install JDK 11

```bash
<a>sudo apt-get install openjdk-11-jdk</a>
```
Now install jenkins by following commands

```bash
   curl -fsSL https://pkg.jenkins.io/debian-stable/jenkins.io.key | sudo tee \
  /usr/share/keyrings/jenkins-keyring.asc > /dev/null

echo deb [signed-by=/usr/share/keyrings/jenkins-keyring.asc] \
  https://pkg.jenkins.io/debian-stable binary/ | sudo tee \
  /etc/apt/sources.list.d/jenkins.list > /dev/null
  
 sudo apt-get update
 
sudo apt-get install jenkins
 
```

After successfull installation start jenkins server
```bash
  sudo systemctl start jenkins.service
```

check the jenkins server is running wihtout any problem
```bash
  sudo systemctl status jenkins
```

Junkins default runnign port is 8080 so just set up it in ufw 
```bash
     sudo ufw allow 8080
     sudo ufw enable 8080
     sudo ufw status 
```

<h3>Most importantly add port 8080 in inbound rule of ec2 instance security group</h3>

Now check the ip

aws_ip:8080

You can see the jenkins interface !!!







