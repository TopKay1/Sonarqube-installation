# Sonarqube-installation
guides to install sonarqube


# Pre req.
1) Any OS
2) Java
3) t2.medium (4gb RAM)
4) open port 9000 (sonarQube default)


# Step 0 - hostname
sudo hostname sonar


 # Step 1 - create sonar user / make admin & su
useradd sonar

sudo echo "sonar ALL=(ALL) NOPASSWD:ALL"|

    sudo tee /etc/sudoers.d/sonar
     
su - sonar


# Step 2 - install wget & unzip
cd /opt => got to opt dir

yum install wget unzip y


# Step 3 - install Java
* 1 wget specific java
* 2 yum install it

sudo wget -c --header "Cookie: oraclelicense=
accept-securebackup-cookie"
http://download.oracle.com/otn-pub/java/jdk
/8u131-b11/d54c1d3a095b4ff2b6607d096fa80163
/jdk-8u131-linux-x64.rpm

sudo yum install jdk-8u131-linux-x64.rpm -y

java -version => verify w/ one "_"


# Step 4 - download Sonarqube 7.8 from site
download sonarqube 7/8 from site with tar /zip url

wget https:/binaries.sonarsource.com/Distribution

/sonarqube/sonarqube-7.8.zip>


# Step 5 - untar /unzip file
tar -xvf <sonarqube-7.8.tar.gz>

unzip <sonarqube-7.8.zip>


# Step 6 - rename
sudo

rm -rf <sonarqube-7.8.zip> => remove zip file

mv sonarqube-7.8/ sonarqube => rename unzip file


# Step 7 - Permissions
* change group owner of dir to sonar
* 775 permission

sudo chown -R sonar:sonar /opt/sonarqube

sudo chmod -R 775 /opt/sonarqube

=> user and group has all rights


# Step 8 - start sonarqube others
sh /opt/sonarqube/bin/linux../sonar.sh start

{sonar.sh  stop, sonar.sh  restart}
