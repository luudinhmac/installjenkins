# Cài đặt gitlab trên centos 7

yum install epel-release -y

yum update -y

**Tắt firewall và SELinux**

sed -i 's/SELINUX=enforcing/SELINUX=disabled/g' /etc/sysconfig/selinux

sed -i 's/SELINUX=enforcing/SELINUX=disabled/g' /etc/selinux/config

systemctl stop firewalld

systemctl disable firewalld

__Cấu hình đồng bộ thời gian__

timedatectl set-timezone Asia/Ho_Chi_Minh

yum -y install chrony

systemctl enable chronyd.service

systemctl restart chronyd.service

chronyc sources

timedatectl set-local-rtc 0


__Cài đặt repo jenkins__

curl --silent --location http://pkg.jenkins-ci.org/redhat-stable/jenkins.repo | sudo tee /etc/yum.repos.d/jenkins.repo

sudo rpm --import https://jenkins-ci.org/redhat/jenkins-ci.org.key

sudo rpm --import https://pkg.jenkins.io/redhat-stable/jenkins.io.key

**Cài đặt jenkins**

sudo yum install jenkins -y

**Khởi động jenkins**

_sudo systemctl start jenkins _
_sudo systemctl enable jenkins_
_sudo systemctl status  jenkins_

**_Mặc định Jenkin chạy port 8080_**

**3. Thiết lập Jenkins**

Truy cập đường dẫn http://10.10.10.20:8080

Tại giao diện sẽ yêu cầu nhập khóa mật khẩu Admin

Khóa bí mật admin chỉ có khi truy cập giao diện lần đầu

Lấy mật khẩu admin tại đường dẫn 

_cat /var/lib/jenkins/secrets/initialAdminPassword_



![](/mkadmin.PNG)

Cài đặt plugin cho jenkins

![](/installplugin.PNG)
![](/installplugin1.PNG)
**Tạo tài khoản jenkins admin**

* Nhập thông tin tài khoản
* Chọn save and continute để tiếp tục
* Save and Finish
* Starting Jenkins
