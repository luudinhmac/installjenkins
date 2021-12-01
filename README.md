# installgitlab
Cài đặt gitlab trên centOS 7

yum install epel-release -y
yum update -y

`Tắt firewall và SELinux
sed -i 's/SELINUX=enforcing/SELINUX=disabled/g' /etc/sysconfig/selinux
sed -i 's/SELINUX=enforcing/SELINUX=disabled/g' /etc/selinux/config
systemctl stop firewalld
systemctl disable firewalld
