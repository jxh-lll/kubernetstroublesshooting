思路：kubectl get nodes 确认kubelet是否正常>
>是:客户端证书失损坏制原始证书
>1: `mkdir .kube `
>2:`sudo cp /etc/kubernets/admin.conf ~/.kube/config`
>3:`sudo chwon $(id -u):$(id -g) /.kube/config`
>否：`sudo crictl ps -a | grep <pod-name>` (会直接访问containers日志输出无需kubelet),查看apiserver控制容器平面。
没有或出现notfound,使用pki证书修复:`sudo kubeadm certs renew all`（注意修复后：客户端管理员证书重新生成需要从新复制启用）
重启kubelet`sudo systemctl restart kubelet`
