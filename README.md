# kubernetstroublesshooting
# jxh-lll china 焦绪红
问题：apiserver carshloopbackoff 导致 The connection to the server *.*.*.*:* was refused - did you specify the right host or port?

                                         >是:客户端证书失损坏制原始证书 1: mkdir .kube 2:sudo cp /etc/kubernets/admin.conf ~/.kube/config3:sudo chwon $(id -u):$(id -g) /.kube/config
思路：kubectl get nodes 确认kubelet是否正常>
                                          >否：crictl(会直接访问containers日志输出无需kubelet),查看apiserver控制容器平面，没有或出现notfound,使用pki证书修复（注意修复后：客户端管理员证书重新生成需要从新复制启用）
