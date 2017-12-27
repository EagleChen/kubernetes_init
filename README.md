# kubernetes_init

install docker, kubernetes and initialize kubernetes cluster by kubeadm

在天朝特殊网络环境下，加速安装docker,kubernetes并创建kubernetes集群

## 如何使用
```
git clone git@github.com:EagleChen/kubernetes_init.git
cd kubernetes_init
# 修改 install.sh
sudo ./install.sh pre
sudo ./install.sh kubernetes
```

## 注意事项
1. 对照着[官方文档](https://kubernetes.io/docs/setup/independent/install-kubeadm/)使用，本脚本几乎按照官方步骤执行，只是修改了各种下载地址，方便国内特殊网络环境使用
2. 根据自己需求修改`install.sh`
3. 为了简单和直观，`install.sh`脚本没有做过多容错处理，当执行错误时(例如忘记修改相关参数)，并不好重新执行一遍，此时应该拷贝出脚本相关内容，手动执行
4. 脚本只装了`master`的相关组件，后续操作(非常类似了，无坑)，需要对照着官方文档进行

## 博客链接
https://www.jianshu.com/p/0e54aa7a20cf
讲了一些细节，仅供参考
