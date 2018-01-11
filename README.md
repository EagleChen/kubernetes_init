# kubernetes_init

install docker, kubernetes and initialize kubernetes cluster by kubeadm

在天朝特殊网络环境下，加速安装docker,kubernetes并创建kubernetes集群

## 如何使用
```
# 安装 master (在master机器上进行)
git clone git@github.com:EagleChen/kubernetes_init.git
cd kubernetes_init
# 修改 install.sh, 一定要(至少)改前面几个变量， 否则并不会执行成功
sudo ./install.sh pre   # 安装 docker、kube* 等基础工具
sudo ./install.sh kubernetes-master   # 利用kubeadm安装master节点
./install.sh post # 安装网络组件

# 等master安装好, 从输出中获取相关参数，然后安装node (在node机器上进行)
git clone git@github.com:EagleChen/kubernetes_init.git
cd kubernetes_init
# 修改 install.sh, 一定要(至少)改前面几个变量， 否则并不会执行成功
sudo ./install.sh pre   # 安装 docker、kube* 等基础工具
sudo ./install.sh kubernetes-node   # 利用kubeadm把node添加进cluster
```

## 注意事项
1. 对照着[官方文档](https://kubernetes.io/docs/setup/independent/install-kubeadm/)使用，本脚本几乎按照官方步骤执行，只是修改了各种下载地址，方便国内特殊网络环境使用
2. 根据自己需求修改`install.sh`
3. 为了简单和直观，`install.sh`脚本没有做过多容错处理，当执行错误时(例如忘记修改相关参数)，并不好重新执行一遍，此时应该拷贝出脚本相关内容，手动执行

## 博客链接
https://www.jianshu.com/p/0e54aa7a20cf
讲了一些细节，仅供参考
