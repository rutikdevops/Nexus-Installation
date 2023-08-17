# Nexus-Installation
# Steps for Nexus Installation

- Create 1 ec2 instance - t2.micro
<img width="948" alt="image" src="https://github.com/rutikdevops/Nexus-Installation/assets/109506158/b568529a-2aed-4409-9371-59ef776d71e2">
<br></br>

```bash
ec2-user
sudo su
yum update -y
hostnamectl set-hostname nexus
ls
```

- Install Java
```bash
yum install java* -y
```


- Install Nexus
```bash
cd /opt
wget https://download.sonatype.com/nexus/3/nexus-3.45.0-01-unix.tar.gz
tar -xvzf nexus-3.45.0-01-unix.tar.gz
mv nexus-3.45.0-01 nexus
cd nexus
```


- Add user Nexus
```bash
sudo adduser nexus
visudo               #(in vi editor press (shift+g)), and then add- (nexus ALL=(ALL)   ALL) next of root)
passwd nexus         #(enter same passwd 2 times)
sudo chown -R nexus:nexus /opt/nexus 
ls -ld /opt/nexus
vi /opt/nexus/bin/nexus.rc
                    # run_as_user="nexus"  (only type nexus in vi editor) 
sudo ln -s /opt/nexus/bin/nexus /etc/init.d/nexus
su - nexus
```


- Start service
```bash
service nexus start
service nexus status
```

- chrome- public ip:8081
- sign in
- username=admin
- passwd=admin123


















