Continuous Integration with Jenkins on Amazon EC2
=================================================

## Initial Setup

### Fixing Locales in RedHat7 on Amazon EC2

```bash
sudo yum update
sudo yum install java-1.8.0-openjdk.x86_64
sudo yum update
```

### Installing Jenkins

```bash
sudo wget -O /etc/yum.repos.d/jenkins.repo http://pkg.jenkins-ci.org/redhat-stable/jenkins.repo
sudo rpm --import http://pkg.jenkins-ci.org/redhat-stable/jenkins-ci.org.key
sudo yum install jenkins
```
### Start Jenkins Service
```
sudo systemctl start jenkins.service
sudo systemctl status jenkins.service
sudo systemctl enable jenkins.service
```

### Start `Jenkins`

- Hostname 

```bash
cat /var/lib/jenkins/secrets/initialAdminPassword
```


