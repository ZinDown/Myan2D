# Myan2D
This Is 2D 3D


{
  "dns": {
    "independent_cache": true,
    "rules": [
      {
        "domain": [
          "dns.google"
        ],
        "server": "dns-direct"
      }
    ],
    "servers": [
      {
        "address": "https://dns.google/dns-query",
        "address_resolver": "dns-direct",
        "strategy": "ipv4_only",
        "tag": "dns-remote"
      },
      {
        "address": "local",
        "address_resolver": "dns-local",
        "detour": "direct",
        "strategy": "ipv4_only",
        "tag": "dns-direct"
      },
      {
        "address": "local",
        "detour": "direct",
        "tag": "dns-local"
      },
      {
        "address": "rcode://success",
        "tag": "dns-block"
      }
    ]
  },
  "inbounds": [
    {
      "listen": "127.0.0.1",
      "listen_port": 6450,
      "override_address": "8.8.8.8",
      "override_port": 53,
      "tag": "dns-in",
      "type": "direct"
    },
    {
      "domain_strategy": "",
      "endpoint_independent_nat": true,
      "inet4_address": [
        "172.19.0.1/28"
      ],
      "mtu": 9000,
      "sniff": true,
      "sniff_override_destination": false,
      "stack": "mixed",
      "tag": "tun-in",
      "type": "tun"
    },
    {
      "domain_strategy": "",
      "listen": "127.0.0.1",
      "listen_port": 2080,
      "sniff": true,
      "sniff_override_destination": false,
      "tag": "mixed-in",
      "type": "mixed"
    }
  ],
  "log": {
    "level": "panic"
  },
  "outbounds": [
    {
      "password": "0b0387b8-5258-386b-8744-dcacb2320d94",
      "server": "3.38.198.76",
      "server_port": 443,
      "tls": {
        "enabled": true,
        "insecure": true,
        "server_name": "AAAAAAAAAAAAAAAAAAA.BILIVIDEO.COM"
      },
      "type": "trojan",
      "domain_strategy": "",
      "tag": "proxy"
    },
    {
      "tag": "direct",
      "type": "direct"
    },
    {
      "tag": "bypass",
      "type": "direct"
    },
    {
      "tag": "block",
      "type": "block"
    },
    {
      "tag": "dns-out",
      "type": "dns"
    }
  ],
  "route": {
    "auto_detect_interface": true,
    "rule_set": [],
    "rules": [
      {
        "outbound": "dns-out",
        "port": [
          53
        ]
      },
      {
        "inbound": [
          "dns-in"
        ],
        "outbound": "dns-out"
      },
      {
        "ip_cidr": [
          "224.0.0.0/3",
          "ff00::/8"
        ],
        "outbound": "block",
        "source_ip_cidr": [
          "224.0.0.0/3",
          "ff00::/8"
        ]
      }
    ]
  }
}



ss://YWVzLTI1Ni1nY206Li4uTW9qaWEgLS0tIEBpcmFuUHduZXIgdGVsZWdyYW0uLi4@116.204.181.102:12492#%F0%9F%87%B9%F0%9F%87%AD-TH-Mojia-Tel-%40iranPwner




