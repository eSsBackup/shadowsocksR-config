## Shadowsocks Config Script

- ###Installation

  - scp
    ```bash 
    scp ~/Github/shadowsocksR-config/shadowsocksR.sh root@ssr2:~
    ```

  - ssh
    ```bash
    ssh root@ssr2
    ```


- ###Key files

  - SS日志文件
    - /var/log/shadowsocks.log
  - ShadowsocksR.sh 日志
  - Shadowsocks.json 配置文件
    - /etc/shadowsocks.json

- ###Commands

  - 判断BBR模块是否工作
    ```bash
    lsmod | grep bbr 
    ```
  - 开启BBR
    ```bash
    modprobe tcp_bbr
    echo "tcp_bbr" >> /etc/modules-load.d/modules.conf
    echo "net.core.default_qdisc=fq" >> /etc/sysctl.conf
    echo "net.ipv4.tcp_congestion_control=bbr" >> /etc/sysctl.conf
    sysctl -p
    sysctl net.ipv4.tcp_available_congestion_control
    sysctl net.ipv4.tcp_congestion_control
    ```
  - 判断内核版本
    ```bash
    uname -r
    ```
