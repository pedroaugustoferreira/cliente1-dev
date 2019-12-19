# cliente1-dev
sed -i 's/88/131/g' /etc/sysconfig/network-scripts/ifcfg-ens192;systemctl restart network
sed -i 's/88/132/g' /etc/sysconfig/network-scripts/ifcfg-ens192;systemctl restart network
sed -i 's/88/133/g' /etc/sysconfig/network-scripts/ifcfg-ens192;systemctl restart network
sed -i 's/88/134/g' /etc/sysconfig/network-scripts/ifcfg-ens192;systemctl restart network
sed -i 's/88/135/g' /etc/sysconfig/network-scripts/ifcfg-ens192;systemctl restart network
sed -i 's/88/136/g' /etc/sysconfig/network-scripts/ifcfg-ens192;systemctl restart network
sed -i 's/88/137/g' /etc/sysconfig/network-scripts/ifcfg-ens192;systemctl restart network

ssh 192.168.100.131 hostnamectl set-hostname lab-pd-node1.cliente1.dev
ssh 192.168.100.132 hostnamectl set-hostname lab-pd-node2.cliente1.dev
ssh 192.168.100.133 hostnamectl set-hostname lab-pd-node3.cliente1.dev
ssh 192.168.100.134 hostnamectl set-hostname lab-pd-node4.cliente1.dev
ssh 192.168.100.135 hostnamectl set-hostname lab-pd-node5.cliente1.dev
ssh 192.168.100.136 hostnamectl set-hostname lab-pd-node6.cliente1.dev
ssh 192.168.100.137 hostnamectl set-hostname lab-pd-node7.cliente1.dev

ssh 192.168.100.131 sed -i 's/lab01.sascar.com/cliente1.dev/g' /etc/sysconfig/network-scripts/ifcfg-ens192
ssh 192.168.100.132 sed -i 's/lab01.sascar.com/cliente1.dev/g' /etc/sysconfig/network-scripts/ifcfg-ens192
ssh 192.168.100.133 sed -i 's/lab01.sascar.com/cliente1.dev/g' /etc/sysconfig/network-scripts/ifcfg-ens192
ssh 192.168.100.134 sed -i 's/lab01.sascar.com/cliente1.dev/g' /etc/sysconfig/network-scripts/ifcfg-ens192
ssh 192.168.100.135 sed -i 's/lab01.sascar.com/cliente1.dev/g' /etc/sysconfig/network-scripts/ifcfg-ens192
ssh 192.168.100.136 sed -i 's/lab01.sascar.com/cliente1.dev/g' /etc/sysconfig/network-scripts/ifcfg-ens192
ssh 192.168.100.137 sed -i 's/lab01.sascar.com/cliente1.dev/g' /etc/sysconfig/network-scripts/ifcfg-ens192


ssh 192.168.100.131 subscription-manager clean
ssh 192.168.100.132 subscription-manager clean
ssh 192.168.100.133 subscription-manager clean
ssh 192.168.100.134 subscription-manager clean
ssh 192.168.100.135 subscription-manager clean
ssh 192.168.100.136 subscription-manager clean
ssh 192.168.100.137 subscription-manager clean

username=XXXX
password=XXXX
ssh 192.168.100.131 subscription-manager register --username $username --password $password
ssh 192.168.100.132 subscription-manager register --username $username --password $password
ssh 192.168.100.133 subscription-manager register --username $username --password $password
ssh 192.168.100.134 subscription-manager register --username $username --password $password
ssh 192.168.100.135 subscription-manager register --username $username --password $password
ssh 192.168.100.136 subscription-manager register --username $username --password $password
ssh 192.168.100.137 subscription-manager register --username $username --password $password

ssh 192.168.100.131 subscription-manager attach --pool=8a85f99b6e12cc13016e3baad78f45f0
ssh 192.168.100.132 subscription-manager attach --pool=8a85f99b6e12cc13016e3baad78f45f0
ssh 192.168.100.133 subscription-manager attach --pool=8a85f99b6e12cc13016e3baad78f45f0
ssh 192.168.100.134 subscription-manager attach --pool=8a85f99b6e12cc13016e3baad78f45f0
ssh 192.168.100.135 subscription-manager attach --pool=8a85f99b6e12cc13016e3baad78f45f0
ssh 192.168.100.136 subscription-manager attach --pool=8a85f99b6e12cc13016e3baad78f45f0
ssh 192.168.100.137 subscription-manager attach --pool=8a85f99b6e12cc13016e3baad78f45f0

ssh 192.168.100.131 yum -y update
ssh 192.168.100.132 yum -y update
ssh 192.168.100.133 yum -y update
ssh 192.168.100.134 yum -y update
ssh 192.168.100.135 yum -y update
ssh 192.168.100.136 yum -y update
ssh 192.168.100.137 yum -y update

ssh 192.168.100.131 yum -y install atomic-openshift-clients openshift-ansible screen wget
ssh 192.168.100.132 yum -y install atomic-openshift-clients openshift-ansible screen wget
ssh 192.168.100.133 yum -y install atomic-openshift-clients openshift-ansible screen wget
ssh 192.168.100.134 yum -y install atomic-openshift-clients openshift-ansible screen wget
ssh 192.168.100.135 yum -y install atomic-openshift-clients openshift-ansible screen wget
ssh 192.168.100.136 yum -y install atomic-openshift-clients openshift-ansible screen wget
ssh 192.168.100.137 yum -y install atomic-openshift-clients openshift-ansible screen wget

ssh 192.168.100.131 subscription-manager repos --enable="rhel-7-server-rpms"  --enable="rhel-7-server-extras-rpms" --enable="rhel-7-server-ose-3.11-rpms" --enable="rhel-7-server-ansible-2.6-rpms"
ssh 192.168.100.132 subscription-manager repos --enable="rhel-7-server-rpms"  --enable="rhel-7-server-extras-rpms" --enable="rhel-7-server-ose-3.11-rpms" --enable="rhel-7-server-ansible-2.6-rpms"
ssh 192.168.100.133 subscription-manager repos --enable="rhel-7-server-rpms"  --enable="rhel-7-server-extras-rpms" --enable="rhel-7-server-ose-3.11-rpms" --enable="rhel-7-server-ansible-2.6-rpms"
ssh 192.168.100.134 subscription-manager repos --enable="rhel-7-server-rpms"  --enable="rhel-7-server-extras-rpms" --enable="rhel-7-server-ose-3.11-rpms" --enable="rhel-7-server-ansible-2.6-rpms"
ssh 192.168.100.135 subscription-manager repos --enable="rhel-7-server-rpms"  --enable="rhel-7-server-extras-rpms" --enable="rhel-7-server-ose-3.11-rpms" --enable="rhel-7-server-ansible-2.6-rpms"
ssh 192.168.100.136 subscription-manager repos --enable="rhel-7-server-rpms"  --enable="rhel-7-server-extras-rpms" --enable="rhel-7-server-ose-3.11-rpms" --enable="rhel-7-server-ansible-2.6-rpms"
ssh 192.168.100.137 subscription-manager repos --enable="rhel-7-server-rpms"  --enable="rhel-7-server-extras-rpms" --enable="rhel-7-server-ose-3.11-rpms" --enable="rhel-7-server-ansible-2.6-rpms"
	




