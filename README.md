# comparison between iptables, ipvs, nftables and iptables-bpf

## About The Project 

Kubernetes provide three kinds of load-balancing strategys: namespace, iptables and ipvs. Namespace is too over-time and almost has been adapted, so most k8s are now using iptables and ipvs. Everyone knows that
iptables has a very bad performance compared with ipvs, but why exactly? What's the difference between iptablse, ipvs, nftables and the new star - iptables-bpf? 

This project is attemped to compare the difference between the architecture of iptables, ipvs, nftables and iptables-bpf, measure the performance loss and update/insert time increment among them. 

### Built With 

* experiment target
    * [iptables](https://netfilter.org/projects/iptables/index.html)
    * [linux virtual server (ipvs)](http://www.linuxvirtualserver.org/)
    * [nftables](https://netfilter.org/projects/nftables/index.html)
    * [bpf-iptables](https://github.com/mbertrone/bpf-iptables)

* performance measurement tools
    * [iperf3](https://iperf.fr/iperf-download.php) for bandwidth
    * simple shell scripts for update/insert time increment

#### ref 

* [benchmarking-nftables](https://developers.redhat.com/blog/2017/04/11/benchmarking-nftables)
* [optimizing-iptables-nft-large-ruleset-performance-in-user-space](https://developers.redhat.com/blog/2020/04/27/optimizing-iptables-nft-large-ruleset-performance-in-user-space)



