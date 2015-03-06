#安装cobaltstrike记录
#
# 
tar zxvf cobaltstrike-trial.tgz

cd cobaltstrike/

#删除试用记录
rm ~/.cobaltstrike.prop

#

#Installation Steps
#1.Start the postgresql database
service postgresql start
#2.(Optional) Make postgresql database start on boot
update-rc.d postgresql enable
#3.Start and stop the Metasploit service (this will setup your database.yml file for you)
service metasploit start 
service metasploit stop
#4.Extract cobaltstrike-trial.tgz
tar zxvf cobaltstrike-trial.tgz
#5.Tell Kali Linux to use Java 1.7 by default
#32-bit Kali Linux: 
update-java-alternatives --jre -s java-1.7.0-openjdk-i386
#64-bit Kali Linx: 
#update-java-alternatives --jre -s java-1.7.0-openjdk-amd64


#run

service postgresql start
cd ~/cobaltstrike
./cobaltstrike
