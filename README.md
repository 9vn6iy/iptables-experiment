# comparison between iptables, ipvs, nftables and iptables-bpf

## About The Project 

Kubernetes provides three load balancing strategies: namespace, iptables and ipvs. Because the namespace is out of 
date, most k8s clusters adope iptables and IPVS strategies. Almose everyone knows that iptables perform poorly 
compared with IPVS, but why exactly? What's the difference between them? 

Besides, linux kernel has changed the firewall rules management system from iptables to nftables, and since the 
[bpf](https://www.kernel.org/doc/Documentation/networking/filter.txt) and [ebpf](https://ebpf.io/) project have been 
in the air, there is also an iptables implementation of bpf 
([iptables-bpf](https://github.com/mbertrone/bpf-iptables)). So we want to compare these techs as well. 

This project is attemped to compare the difference between the architecture of iptables, ipvs, nftables and 
iptables-bpf, measure the performance loss and update/insert time increment among them. 

### Built With 

* experiment target
    * [iptables](https://netfilter.org/projects/iptables/index.html)
    * [linux virtual server (ipvs)](http://www.linuxvirtualserver.org/)
    * [nftables](https://netfilter.org/projects/nftables/index.html)
    * [bpf-iptables](https://github.com/mbertrone/bpf-iptables)

* performance measurement tools
    * [iperf3](https://iperf.fr/iperf-download.php) for bandwidth measurement
    * simple shell scripts for update/insert time increment

## Getting Started 

### Experiment Environment

| Environment  |       Version |
| ------------ | ------------- |
| CentOS Linux |      7.3.1611 |
| Linux Kernel | 5.10.37-1.el7 |
| iperf3       |          3.17 |
| docker       |    18.06.3-ce |
| iptables     |        1.4.21 |
| ipvsadm      |          1.27 |
| bash         |        4.2.46 |
|              |               |


#### ref 

* [benchmarking-nftables](https://developers.redhat.com/blog/2017/04/11/benchmarking-nftables)
* [optimizing-iptables-nft-large-ruleset-performance-in-user-space](https://developers.redhat.com/blog/2020/04/27/optimizing-iptables-nft-large-ruleset-performance-in-user-space)



