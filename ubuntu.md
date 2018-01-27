Continuous Integration with Jenkins on Amazon EC2
=================================================

## Initial Setup

### Fixing Locales in Ubuntu 14.04 on Amazon EC2

```bash
sudo apt-get install language-pack-en
sudo apt-get install python-software-properties
sudo apt-add-repository ppa:webupd8team/java
sudo apt-get update
sudo apt-get install oracle-java8-installer
```

### Installing Jenkins

```bash
wget -q -O - https://pkg.jenkins.io/debian/jenkins-ci.org.key | sudo apt-key add -
sudo sh -c 'echo deb http://pkg.jenkins.io/debian-stable binary/ > /etc/apt/sources.list.d/jenkins.list'
sudo apt-get update
sudo apt-get install jenkins
```

## Installing and Configuring Apache Default jenkins runs on 8080

### Installing Apache

```bash
sudo apt-get install apache2
sudo a2enmod proxy
sudo a2enmod proxy_http
```
### How to Get Hostname

- Open terminal and enter hostname you will get hostname of you ec2 machine

```bash
hostname
```

### `/etc/apache2/sites-available/jenkins.conf`

```bash
<VirtualHost *:80>
	ServerName HOSTNAME
	ProxyRequests Off
	<Proxy *>
		Order deny,allow
		Allow from all
	</Proxy>
	ProxyPreserveHost on
	ProxyPass / http://localhost:8080/
</VirtualHost>
```

### Enabling `jenkins.conf`

```bash
sudo a2ensite jenkins
sudo service apache2 reload
```
### Start `Jenkins`

- Hostname 

```
sudo service jenkins start
cat /var/lib/jenkins/secrets/initialAdminPassword
```
