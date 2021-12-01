# installgitlab
Cài đặt gitlab trên centOS 7

yum install epel-release -y
yum update -y

Tắt firewall và SELinux

sed -i 's/SELINUX=enforcing/SELINUX=disabled/g' /etc/sysconfig/selinux

sed -i 's/SELINUX=enforcing/SELINUX=disabled/g' /etc/selinux/config

systemctl stop firewalld

systemctl disable firewalld

Cấu hình đồng bộ thời gian

timedatectl set-timezone Asia/Ho_Chi_Minh

yum -y install chrony

systemctl enable chronyd.service

systemctl restart chronyd.service

chronyc sources

timedatectl set-local-rtc 0
