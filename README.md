# har

# 简介
har是国产化集群编排系统

> har = K8S+UI管理(类似rancher)+etcd+coredns+ingress+cni+....
> 
> 一个小小的exe, 完成了所有K8S全家桶, 所有的事情让har管理, 不用运维, 不用每年更新证书
easy quick and light

# 使用方法
前提: 
1. 保证该机器装有docker
2. 使用root或者sudo权限操作

下载:
1. 下载对应架构的har, 如x86下, 下载: har_x86_64.tar.gz
2. 解压出程序: har, 可以放置任意服务器目录
3. chmod +x har

运行:
```
./har start
```

停止:
```
./har stop
```

# 说明 && 对比K8S
1. 他比K8S更加兼容国产化硬件和国产化系统, 有针对性的对他们做了调优
2. 网络适应性更强, har可以让互联网上的机器组集群, 他可以穿NAT, 他可以链式组集群, 只要他们两两网络能互通, 那么整个集群网络都可以打同
3. 他没有master概念, 全部资源池结构,引入共识算法取带raft, 任何多台机器中挂掉任意台机器, 他依然能正常工作
4. 他轻量, 稳定工作后, 内存100M, cpu 3%
5. 他all in one, 他的功能含盖K8S, cni, dns, hub, ingress, WEB可视化UI管理, 后续还会加入可视化监控系统等功能
6. 从其他K8S集群导出yaml, 在har的web中导入即可使用
7. 目前还不支持nas的vpc磁盘映射, 我们后面会加的


# 端口暴露 && 运维
默认端口是3080 (为了避开很多xxx项目中80和443的xxx)
1. 导入业务服务的ingress.yaml后, 即可在 xxx.xxx.xxx.xxx:3080访问业务
2. 我们复用3080端口, 其中有个特殊uri作为运维管理web, xxx.xxx.xxx.xxx:3080/har  (har start后即可访问)

# 源码
- 为了行业客户的代码安全, 暂时不考虑开源
- 实在需要的, 或者对产品有定制需求的, 可以通过下面的联系方式联系

# 联系方式
- 微信: quange805557  (个人生活微信, 加好友时请备注:har定制/har源码等)
- 邮箱: minchieh@hotmail.com

# issus
如果该产品有bug, 请提issus, 以及日志(日志在/var/lib/har目录), 万分感谢
