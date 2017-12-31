Example
=======

below is an example parameter file as used by the lifecycle management playbooks:

    ---
    tenant:
      name:        "Clearwater_SOL"
      description: "Clearwater tenant in SOL-B data center"
      password:    "secret"
      cloud:       "SOL-B"

    security_groups:
    - Clearwater_SOL_jumphost_svc2
    - Clearwater_SOL_jumphost_oam
    - Clearwater_SOL_proxy_oam
    - Clearwater_SOL_proxy_m2m1
    - Clearwater_SOL_proxy_svc1
    - Clearwater_SOL_bono_oam
    - Clearwater_SOL_bono_m2m1
    - Clearwater_SOL_bono_svc1
    - Clearwater_SOL_sprout_oam
    - Clearwater_SOL_sprout_m2m1
    - Clearwater_SOL_vellum_oam
    - Clearwater_SOL_vellum_m2m1
    - Clearwater_SOL_vellum_m2m2
    - Clearwater_SOL_dime_oam
    - Clearwater_SOL_dime_m2m1
    - Clearwater_SOL_homer_oam
    - Clearwater_SOL_homer_m2m1
    - Clearwater_SOL_ellis_oam
    - Clearwater_SOL_ellis_m2m1

    external_security_group_rules:
    - group:            Clearwater_SOL_jumphost_svc2
      direction:        ingress
      ethertype:        IPv4
      protocol:         tcp
      min:              22
      max:              22
      mode:             cidr
      remote_ip_prefix: 0.0.0.0/0
    - group:            Clearwater_SOL_proxy_svc1
      direction:        egress
      ethertype:        IPv4
      protocol:         tcp
      min:              80
      max:              80
      mode:             cidr
      remote_ip_prefix: 0.0.0.0/0
    - group:            Clearwater_SOL_proxy_svc1
      direction:        egress
      ethertype:        IPv4
      protocol:         tcp
      min:              443
      max:              443
      mode:             cidr
      remote_ip_prefix: 0.0.0.0/0
    - group:            Clearwater_SOL_proxy_svc1
      direction:        egress
      ethertype:        IPv4
      protocol:         tcp
      min:              3128
      max:              3128
      mode:             cidr
      remote_ip_prefix: 0.0.0.0/0
    - group:            Clearwater_SOL_proxy_svc1
      direction:        egress
      ethertype:        IPv4
      protocol:         tcp
      min:              8080
      max:              8080
      mode:             cidr
      remote_ip_prefix: 0.0.0.0/0
    - group:            Clearwater_SOL_proxy_svc1
      direction:        egress
      ethertype:        IPv4
      protocol:         tcp
      min:              8443
      max:              8443
      mode:             cidr
      remote_ip_prefix: 0.0.0.0/0
    - group:            Clearwater_SOL_bono_svc1
      direction:        ingress
      ethertype:        IPv4
      protocol:         tcp
      min:              5060
      max:              5062
      mode:             cidr
      remote_ip_prefix: 0.0.0.0/0
    - group:            Clearwater_SOL_bono_svc1
      direction:        ingress
      ethertype:        IPv4
      protocol:         udp
      min:              5060
      max:              5062
      mode:             cidr
      remote_ip_prefix: 0.0.0.0/0
    - group:            Clearwater_SOL_bono_svc1
      direction:        ingress
      ethertype:        IPv4
      protocol:         udp
      min:              32768
      max:              65535
      mode:             cidr
      remote_ip_prefix: 0.0.0.0/0
    - group:            Clearwater_SOL_ellis_oam
      direction:        ingress
      ethertype:        IPv4
      protocol:         tcp
      min:              80
      max:              80
      mode:             cidr
      remote_ip_prefix: 0.0.0.0/0
    - group:            Clearwater_SOL_ellis_oam
      direction:        ingress
      ethertype:        IPv4
      protocol:         tcp
      min:              443
      max:              443
      mode:             cidr
      remote_ip_prefix: 0.0.0.0/0

    internal_security_group_rules:
    - group:            Clearwater_SOL_jumphost_oam
      direction:        egress
      ethertype:        IPv4
      protocol:         tcp
      min:              22
      max:              22
      mode:             group
      remote_group:     Clearwater_SOL_proxy_oam
    - group:            Clearwater_SOL_jumphost_oam
      direction:        egress
      ethertype:        IPv4
      protocol:         tcp
      min:              22
      max:              22
      mode:             group
      remote_group:     Clearwater_SOL_sprout_oam
    - group:            Clearwater_SOL_jumphost_oam
      direction:        egress
      ethertype:        IPv4
      protocol:         tcp
      min:              22
      max:              22
      mode:             group
      remote_group:     Clearwater_SOL_bono_oam
    - group:            Clearwater_SOL_jumphost_oam
      direction:        egress
      ethertype:        IPv4
      protocol:         tcp
      min:              22
      max:              22
      mode:             group
      remote_group:     Clearwater_SOL_dime_oam
    - group:            Clearwater_SOL_jumphost_oam
      direction:        egress
      ethertype:        IPv4
      protocol:         tcp
      min:              22
      max:              22
      mode:             group
      remote_group:     Clearwater_SOL_homer_oam
    - group:            Clearwater_SOL_jumphost_oam
      direction:        egress
      ethertype:        IPv4
      protocol:         tcp
      min:              22
      max:              22
      mode:             group
      remote_group:     Clearwater_SOL_vellum_oam
    - group:            Clearwater_SOL_jumphost_oam
      direction:        egress
      ethertype:        IPv4
      protocol:         tcp
      min:              22
      max:              22
      mode:             group
      remote_group:     Clearwater_SOL_ellis_oam
    - group:            Clearwater_SOL_jumphost_oam
      direction:        egress
      ethertype:        IPv4
      protocol:         tcp
      min:              80
      max:              80
      mode:             group
      remote_group:     Clearwater_SOL_ellis_oam
    - group:            Clearwater_SOL_jumphost_oam
      direction:        egress
      ethertype:        IPv4
      protocol:         tcp
      min:              443
      max:              443
      mode:             group
      remote_group:     Clearwater_SOL_ellis_oam
    - group:            Clearwater_SOL_proxy_oam
      direction:        ingress
      ethertype:        IPv4
      protocol:         tcp
      min:              22
      max:              22
      mode:             group
      remote_group:     Clearwater_SOL_jumphost_oam
    - group:            Clearwater_SOL_proxy_m2m1
      direction:        ingress
      ethertype:        IPv4
      protocol:         tcp
      min:              3128
      max:              3128
      mode:             group
      remote_group:     Clearwater_SOL_bono_m2m1
    - group:            Clearwater_SOL_proxy_m2m1
      direction:        ingress
      ethertype:        IPv4
      protocol:         udp
      min:              53
      max:              53
      mode:             group
      remote_group:     Clearwater_SOL_bono_m2m1
    - group:            Clearwater_SOL_proxy_m2m1
      direction:        ingress
      ethertype:        IPv4
      protocol:         tcp
      min:              3128
      max:              3128
      mode:             group
      remote_group:     Clearwater_SOL_sprout_m2m1
    - group:            Clearwater_SOL_proxy_m2m1
      direction:        ingress
      ethertype:        IPv4
      protocol:         udp
      min:              53
      max:              53
      mode:             group
      remote_group:     Clearwater_SOL_sprout_m2m1
    - group:            Clearwater_SOL_proxy_m2m1
      direction:        ingress
      ethertype:        IPv4
      protocol:         tcp
      min:              3128
      max:              3128
      mode:             group
      remote_group:     Clearwater_SOL_vellum_m2m1
    - group:            Clearwater_SOL_proxy_m2m1
      direction:        ingress
      ethertype:        IPv4
      protocol:         udp
      min:              53
      max:              53
      mode:             group
      remote_group:     Clearwater_SOL_vellum_m2m1
    - group:            Clearwater_SOL_proxy_m2m1
      direction:        ingress
      ethertype:        IPv4
      protocol:         tcp
      min:              3128
      max:              3128
      mode:             group
      remote_group:     Clearwater_SOL_dime_m2m1
    - group:            Clearwater_SOL_proxy_m2m1
      direction:        ingress
      ethertype:        IPv4
      protocol:         udp
      min:              53
      max:              53
      mode:             group
      remote_group:     Clearwater_SOL_dime_m2m1
    - group:            Clearwater_SOL_proxy_m2m1
      direction:        ingress
      ethertype:        IPv4
      protocol:         tcp
      min:              3128
      max:              3128
      mode:             group
      remote_group:     Clearwater_SOL_homer_m2m1
    - group:            Clearwater_SOL_proxy_m2m1
      direction:        ingress
      ethertype:        IPv4
      protocol:         udp
      min:              53
      max:              53
      mode:             group
      remote_group:     Clearwater_SOL_homer_m2m1
    - group:            Clearwater_SOL_proxy_m2m1
      direction:        ingress
      ethertype:        IPv4
      protocol:         tcp
      min:              3128
      max:              3128
      mode:             group
      remote_group:     Clearwater_SOL_ellis_m2m1
    - group:            Clearwater_SOL_proxy_m2m1
      direction:        ingress
      ethertype:        IPv4
      protocol:         udp
      min:              53
      max:              53
      mode:             group
      remote_group:     Clearwater_SOL_ellis_m2m1
    - group:            Clearwater_SOL_bono_oam
      direction:        ingress
      ethertype:        IPv4
      protocol:         tcp
      min:              22
      max:              22
      mode:             group
      remote_group:     Clearwater_SOL_jumphost_oam
    - group:            Clearwater_SOL_bono_m2m1
      direction:        egress
      ethertype:        IPv4
      protocol:         tcp
      min:              3128
      max:              3128
      mode:             group
      remote_group:     Clearwater_SOL_proxy_m2m1
    - group:            Clearwater_SOL_bono_m2m1
      direction:        egress
      ethertype:        IPv4
      protocol:         tcp
      min:              5052
      max:              5052
      mode:             group
      remote_group:     Clearwater_SOL_sprout_m2m1
    - group:            Clearwater_SOL_bono_m2m1
      direction:        egress
      ethertype:        IPv4
      protocol:         tcp
      min:              5054
      max:              5054
      mode:             group
      remote_group:     Clearwater_SOL_sprout_m2m1
    - group:            Clearwater_SOL_bono_m2m1
      direction:        egress
      ethertype:        IPv4
      protocol:         tcp
      min:              8888
      max:              8888
      mode:             group
      remote_group:     Clearwater_SOL_dime_m2m1
    - group:            Clearwater_SOL_bono_m2m1
      direction:        egress
      ethertype:        IPv4
      protocol:         tcp
      min:              10888
      max:              10888
      mode:             group
      remote_group:     Clearwater_SOL_dime_m2m1
    - group:            Clearwater_SOL_bono_m2m1
      direction:        egress
      ethertype:        IPv4
      protocol:         udp
      min:              53
      max:              53
      mode:             group
      remote_group:     Clearwater_SOL_proxy_m2m1
    - group:            Clearwater_SOL_bono_m2m1
      direction:        egress
      ethertype:        IPv4
      protocol:         tcp
      min:              2380
      max:              2380
      mode:             group
      remote_group:     Clearwater_SOL_ellis_m2m1
    - group:            Clearwater_SOL_bono_m2m1
      direction:        egress
      ethertype:        IPv4
      protocol:         tcp
      min:              4000
      max:              4000
      mode:             group
      remote_group:     Clearwater_SOL_ellis_m2m1
    - group:            Clearwater_SOL_bono_m2m1
      direction:        egress
      ethertype:        IPv4
      protocol:         tcp
      min:              2380
      max:              2380
      mode:             group
      remote_group:     Clearwater_SOL_sprout_m2m1
    - group:            Clearwater_SOL_bono_m2m1
      direction:        egress
      ethertype:        IPv4
      protocol:         tcp
      min:              4000
      max:              4000
      mode:             group
      remote_group:     Clearwater_SOL_sprout_m2m1
    - group:            Clearwater_SOL_bono_m2m1
      direction:        egress
      ethertype:        IPv4
      protocol:         tcp
      min:              2380
      max:              2380
      mode:             group
      remote_group:     Clearwater_SOL_homer_m2m1
    - group:            Clearwater_SOL_bono_m2m1
      direction:        egress
      ethertype:        IPv4
      protocol:         tcp
      min:              4000
      max:              4000
      mode:             group
      remote_group:     Clearwater_SOL_homer_m2m1
    - group:            Clearwater_SOL_bono_m2m1
      direction:        egress
      ethertype:        IPv4
      protocol:         tcp
      min:              2380
      max:              2380
      mode:             group
      remote_group:     Clearwater_SOL_dime_m2m1
    - group:            Clearwater_SOL_bono_m2m1
      direction:        egress
      ethertype:        IPv4
      protocol:         tcp
      min:              4000
      max:              4000
      mode:             group
      remote_group:     Clearwater_SOL_dime_m2m1
    - group:            Clearwater_SOL_bono_m2m1
      direction:        egress
      ethertype:        IPv4
      protocol:         tcp
      min:              2380
      max:              2380
      mode:             group
      remote_group:     Clearwater_SOL_vellum_m2m1
    - group:            Clearwater_SOL_bono_m2m1
      direction:        egress
      ethertype:        IPv4
      protocol:         tcp
      min:              4000
      max:              4000
      mode:             group
      remote_group:     Clearwater_SOL_vellum_m2m1
    - group:            Clearwater_SOL_bono_m2m1
      direction:        ingress
      ethertype:        IPv4
      protocol:         tcp
      min:              5058
      max:              5058
      mode:             group
      remote_group:     Clearwater_SOL_sprout_m2m1
    - group:            Clearwater_SOL_bono_m2m1
      direction:        ingress
      ethertype:        IPv4
      protocol:         tcp
      min:              2380
      max:              2380
      mode:             group
      remote_group:     Clearwater_SOL_sprout_m2m1
    - group:            Clearwater_SOL_bono_m2m1
      direction:        ingress
      ethertype:        IPv4
      protocol:         tcp
      min:              4000
      max:              4000
      mode:             group
      remote_group:     Clearwater_SOL_sprout_m2m1
    - group:            Clearwater_SOL_bono_m2m1
      direction:        ingress
      ethertype:        IPv4
      protocol:         tcp
      min:              2380
      max:              2380
      mode:             group
      remote_group:     Clearwater_SOL_vellum_m2m1
    - group:            Clearwater_SOL_bono_m2m1
      direction:        ingress
      ethertype:        IPv4
      protocol:         tcp
      min:              4000
      max:              4000
      mode:             group
      remote_group:     Clearwater_SOL_vellum_m2m1
    - group:            Clearwater_SOL_bono_m2m1
      direction:        ingress
      ethertype:        IPv4
      protocol:         tcp
      min:              2380
      max:              2380
      mode:             group
      remote_group:     Clearwater_SOL_dime_m2m1
    - group:            Clearwater_SOL_bono_m2m1
      direction:        ingress
      ethertype:        IPv4
      protocol:         tcp
      min:              4000
      max:              4000
      mode:             group
      remote_group:     Clearwater_SOL_dime_m2m1
    - group:            Clearwater_SOL_bono_m2m1
      direction:        ingress
      ethertype:        IPv4
      protocol:         tcp
      min:              2380
      max:              2380
      mode:             group
      remote_group:     Clearwater_SOL_homer_m2m1
    - group:            Clearwater_SOL_bono_m2m1
      direction:        ingress
      ethertype:        IPv4
      protocol:         tcp
      min:              4000
      max:              4000
      mode:             group
      remote_group:     Clearwater_SOL_homer_m2m1
    - group:            Clearwater_SOL_bono_m2m1
      direction:        ingress
      ethertype:        IPv4
      protocol:         tcp
      min:              2380
      max:              2380
      mode:             group
      remote_group:     Clearwater_SOL_ellis_m2m1
    - group:            Clearwater_SOL_bono_m2m1
      direction:        ingress
      ethertype:        IPv4
      protocol:         tcp
      min:              4000
      max:              4000
      mode:             group
      remote_group:     Clearwater_SOL_ellis_m2m1
    - group:            Clearwater_SOL_sprout_oam
      direction:        ingress
      ethertype:        IPv4
      protocol:         tcp
      min:              22
      max:              22
      mode:             group
      remote_group:     Clearwater_SOL_jumphost_oam
    - group:            Clearwater_SOL_sprout_m2m1
      direction:        ingress
      ethertype:        IPv4
      protocol:         tcp
      min:              5052
      max:              5052
      mode:             group
      remote_group:     Clearwater_SOL_bono_m2m1
    - group:            Clearwater_SOL_sprout_m2m1
      direction:        ingress
      ethertype:        IPv4
      protocol:         tcp
      min:              5054
      max:              5054
      mode:             group
      remote_group:     Clearwater_SOL_bono_m2m1
    - group:            Clearwater_SOL_sprout_m2m1
      direction:        ingress
      ethertype:        IPv4
      protocol:         tcp
      min:              2380
      max:              2380
      mode:             group
      remote_group:     Clearwater_SOL_bono_m2m1
    - group:            Clearwater_SOL_sprout_m2m1
      direction:        ingress
      ethertype:        IPv4
      protocol:         tcp
      min:              4000
      max:              4000
      mode:             group
      remote_group:     Clearwater_SOL_bono_m2m1
    - group:            Clearwater_SOL_sprout_m2m1
      direction:        egress
      ethertype:        IPv4
      protocol:         tcp
      min:              3128
      max:              3128
      mode:             group
      remote_group:     Clearwater_SOL_proxy_m2m1
    - group:            Clearwater_SOL_sprout_m2m1
      direction:        egress
      ethertype:        IPv4
      protocol:         tcp
      min:              7253
      max:              7253
      mode:             group
      remote_group:     Clearwater_SOL_vellum_m2m1
    - group:            Clearwater_SOL_sprout_m2m1
      direction:        egress
      ethertype:        IPv4
      protocol:         tcp
      min:              9160
      max:              9160
      mode:             group
      remote_group:     Clearwater_SOL_vellum_m2m1
    - group:            Clearwater_SOL_sprout_m2m1
      direction:        egress
      ethertype:        IPv4
      protocol:         tcp
      min:              8888
      max:              8888
      mode:             group
      remote_group:     Clearwater_SOL_dime_m2m1
    - group:            Clearwater_SOL_sprout_m2m1
      direction:        egress
      ethertype:        IPv4
      protocol:         tcp
      min:              10888
      max:              10888
      mode:             group
      remote_group:     Clearwater_SOL_dime_m2m1
    - group:            Clearwater_SOL_sprout_m2m1
      direction:        egress
      ethertype:        IPv4
      protocol:         tcp
      min:              7888
      max:              7888
      mode:             group
      remote_group:     Clearwater_SOL_homer_m2m1
    - group:            Clearwater_SOL_sprout_m2m1
      direction:        egress
      ethertype:        IPv4
      protocol:         tcp
      min:              5058
      max:              5058
      mode:             group
      remote_group:     Clearwater_SOL_bono_m2m1
    - group:            Clearwater_SOL_sprout_m2m1
      direction:        egress
      ethertype:        IPv4
      protocol:         udp
      min:              53
      max:              53
      mode:             group
      remote_group:     Clearwater_SOL_proxy_m2m1
    - group:            Clearwater_SOL_sprout_m2m1
      direction:        egress
      ethertype:        IPv4
      protocol:         tcp
      min:              2380
      max:              2380
      mode:             group
      remote_group:     Clearwater_SOL_ellis_m2m1
    - group:            Clearwater_SOL_sprout_m2m1
      direction:        egress
      ethertype:        IPv4
      protocol:         tcp
      min:              4000
      max:              4000
      mode:             group
      remote_group:     Clearwater_SOL_ellis_m2m1
    - group:            Clearwater_SOL_sprout_m2m1
      direction:        egress
      ethertype:        IPv4
      protocol:         tcp
      min:              2380
      max:              2380
      mode:             group
      remote_group:     Clearwater_SOL_bono_m2m1
    - group:            Clearwater_SOL_sprout_m2m1
      direction:        egress
      ethertype:        IPv4
      protocol:         tcp
      min:              4000
      max:              4000
      mode:             group
      remote_group:     Clearwater_SOL_bono_m2m1
    - group:            Clearwater_SOL_sprout_m2m1
      direction:        egress
      ethertype:        IPv4
      protocol:         tcp
      min:              2380
      max:              2380
      mode:             group
      remote_group:     Clearwater_SOL_homer_m2m1
    - group:            Clearwater_SOL_sprout_m2m1
      direction:        egress
      ethertype:        IPv4
      protocol:         tcp
      min:              4000
      max:              4000
      mode:             group
      remote_group:     Clearwater_SOL_homer_m2m1
    - group:            Clearwater_SOL_sprout_m2m1
      direction:        egress
      ethertype:        IPv4
      protocol:         tcp
      min:              2380
      max:              2380
      mode:             group
      remote_group:     Clearwater_SOL_dime_m2m1
    - group:            Clearwater_SOL_sprout_m2m1
      direction:        egress
      ethertype:        IPv4
      protocol:         tcp
      min:              4000
      max:              4000
      mode:             group
      remote_group:     Clearwater_SOL_dime_m2m1
    - group:            Clearwater_SOL_sprout_m2m1
      direction:        egress
      ethertype:        IPv4
      protocol:         tcp
      min:              2380
      max:              2380
      mode:             group
      remote_group:     Clearwater_SOL_vellum_m2m1
    - group:            Clearwater_SOL_sprout_m2m1
      direction:        egress
      ethertype:        IPv4
      protocol:         tcp
      min:              4000
      max:              4000
      mode:             group
      remote_group:     Clearwater_SOL_vellum_m2m1
    - group:            Clearwater_SOL_sprout_m2m1
      direction:        egress
      ethertype:        IPv4
      protocol:         tcp
      min:              11311
      max:              11311
      mode:             group
      remote_group:     Clearwater_SOL_vellum_m2m1
    - group:            Clearwater_SOL_sprout_m2m1
      direction:        ingress
      ethertype:        IPv4
      protocol:         tcp
      min:              9888
      max:              9888
      mode:             group
      remote_group:     Clearwater_SOL_vellum_m2m1
    - group:            Clearwater_SOL_sprout_m2m1
      direction:        ingress
      ethertype:        IPv4
      protocol:         tcp
      min:              2380
      max:              2380
      mode:             group
      remote_group:     Clearwater_SOL_vellum_m2m1
    - group:            Clearwater_SOL_sprout_m2m1
      direction:        ingress
      ethertype:        IPv4
      protocol:         tcp
      min:              4000
      max:              4000
      mode:             group
      remote_group:     Clearwater_SOL_vellum_m2m1
    - group:            Clearwater_SOL_sprout_m2m1
      direction:        ingress
      ethertype:        IPv4
      protocol:         tcp
      min:              9888
      max:              9888
      mode:             group
      remote_group:     Clearwater_SOL_dime_m2m1
    - group:            Clearwater_SOL_sprout_m2m1
      direction:        ingress
      ethertype:        IPv4
      protocol:         tcp
      min:              2380
      max:              2380
      mode:             group
      remote_group:     Clearwater_SOL_dime_m2m1
    - group:            Clearwater_SOL_sprout_m2m1
      direction:        ingress
      ethertype:        IPv4
      protocol:         tcp
      min:              4000
      max:              4000
      mode:             group
      remote_group:     Clearwater_SOL_dime_m2m1
    - group:            Clearwater_SOL_sprout_m2m1
      direction:        ingress
      ethertype:        IPv4
      protocol:         tcp
      min:              2380
      max:              2380
      mode:             group
      remote_group:     Clearwater_SOL_homer_m2m1
    - group:            Clearwater_SOL_sprout_m2m1
      direction:        ingress
      ethertype:        IPv4
      protocol:         tcp
      min:              4000
      max:              4000
      mode:             group
      remote_group:     Clearwater_SOL_homer_m2m1
    - group:            Clearwater_SOL_sprout_m2m1
      direction:        ingress
      ethertype:        IPv4
      protocol:         tcp
      min:              2380
      max:              2380
      mode:             group
      remote_group:     Clearwater_SOL_ellis_m2m1
    - group:            Clearwater_SOL_sprout_m2m1
      direction:        ingress
      ethertype:        IPv4
      protocol:         tcp
      min:              4000
      max:              4000
      mode:             group
      remote_group:     Clearwater_SOL_ellis_m2m1
    - group:            Clearwater_SOL_vellum_oam
      direction:        ingress
      ethertype:        IPv4
      protocol:         tcp
      min:              22
      max:              22
      mode:             group
      remote_group:     Clearwater_SOL_jumphost_oam
    - group:            Clearwater_SOL_vellum_m2m1
      direction:        ingress
      ethertype:        IPv4
      protocol:         tcp
      min:              2380
      max:              2380
      mode:             group
      remote_group:     Clearwater_SOL_bono_m2m1
    - group:            Clearwater_SOL_vellum_m2m1
      direction:        ingress
      ethertype:        IPv4
      protocol:         tcp
      min:              4000
      max:              4000
      mode:             group
      remote_group:     Clearwater_SOL_bono_m2m1
    - group:            Clearwater_SOL_vellum_m2m1
      direction:        ingress
      ethertype:        IPv4
      protocol:         tcp
      min:              7253
      max:              7253
      mode:             group
      remote_group:     Clearwater_SOL_sprout_m2m1
    - group:            Clearwater_SOL_vellum_m2m1
      direction:        ingress
      ethertype:        IPv4
      protocol:         tcp
      min:              9160
      max:              9160
      mode:             group
      remote_group:     Clearwater_SOL_sprout_m2m1
    - group:            Clearwater_SOL_vellum_m2m1
      direction:        ingress
      ethertype:        IPv4
      protocol:         tcp
      min:              2380
      max:              2380
      mode:             group
      remote_group:     Clearwater_SOL_sprout_m2m1
    - group:            Clearwater_SOL_vellum_m2m1
      direction:        ingress
      ethertype:        IPv4
      protocol:         tcp
      min:              4000
      max:              4000
      mode:             group
      remote_group:     Clearwater_SOL_sprout_m2m1
    - group:            Clearwater_SOL_vellum_m2m1
      direction:        ingress
      ethertype:        IPv4
      protocol:         tcp
      min:              11311
      max:              11311
      mode:             group
      remote_group:     Clearwater_SOL_sprout_m2m1
    - group:            Clearwater_SOL_vellum_m2m1
      direction:        egress
      ethertype:        IPv4
      protocol:         tcp
      min:              3128
      max:              3128
      mode:             group
      remote_group:     Clearwater_SOL_proxy_m2m1
    - group:            Clearwater_SOL_vellum_m2m1
      direction:        egress
      ethertype:        IPv4
      protocol:         tcp
      min:              9888
      max:              9888
      mode:             group
      remote_group:     Clearwater_SOL_sprout_m2m1
    - group:            Clearwater_SOL_vellum_m2m1
      direction:        egress
      ethertype:        IPv4
      protocol:         tcp
      min:              8888
      max:              8888
      mode:             group
      remote_group:     Clearwater_SOL_dime_m2m1
    - group:            Clearwater_SOL_vellum_m2m1
      direction:        egress
      ethertype:        IPv4
      protocol:         tcp
      min:              10888
      max:              10888
      mode:             group
      remote_group:     Clearwater_SOL_dime_m2m1
    - group:            Clearwater_SOL_vellum_m2m1
      direction:        egress
      ethertype:        IPv4
      protocol:         udp
      min:              53
      max:              53
      mode:             group
      remote_group:     Clearwater_SOL_proxy_m2m1
    - group:            Clearwater_SOL_vellum_m2m1
      direction:        egress
      ethertype:        IPv4
      protocol:         tcp
      min:              2380
      max:              2380
      mode:             group
      remote_group:     Clearwater_SOL_ellis_m2m1
    - group:            Clearwater_SOL_vellum_m2m1
      direction:        egress
      ethertype:        IPv4
      protocol:         tcp
      min:              4000
      max:              4000
      mode:             group
      remote_group:     Clearwater_SOL_ellis_m2m1
    - group:            Clearwater_SOL_vellum_m2m1
      direction:        egress
      ethertype:        IPv4
      protocol:         tcp
      min:              2380
      max:              2380
      mode:             group
      remote_group:     Clearwater_SOL_sprout_m2m1
    - group:            Clearwater_SOL_vellum_m2m1
      direction:        egress
      ethertype:        IPv4
      protocol:         tcp
      min:              4000
      max:              4000
      mode:             group
      remote_group:     Clearwater_SOL_sprout_m2m1
    - group:            Clearwater_SOL_vellum_m2m1
      direction:        egress
      ethertype:        IPv4
      protocol:         tcp
      min:              2380
      max:              2380
      mode:             group
      remote_group:     Clearwater_SOL_homer_m2m1
    - group:            Clearwater_SOL_vellum_m2m1
      direction:        egress
      ethertype:        IPv4
      protocol:         tcp
      min:              4000
      max:              4000
      mode:             group
      remote_group:     Clearwater_SOL_homer_m2m1
    - group:            Clearwater_SOL_vellum_m2m1
      direction:        egress
      ethertype:        IPv4
      protocol:         tcp
      min:              2380
      max:              2380
      mode:             group
      remote_group:     Clearwater_SOL_dime_m2m1
    - group:            Clearwater_SOL_vellum_m2m1
      direction:        egress
      ethertype:        IPv4
      protocol:         tcp
      min:              4000
      max:              4000
      mode:             group
      remote_group:     Clearwater_SOL_dime_m2m1
    - group:            Clearwater_SOL_vellum_m2m1
      direction:        egress
      ethertype:        IPv4
      protocol:         tcp
      min:              2380
      max:              2380
      mode:             group
      remote_group:     Clearwater_SOL_bono_m2m1
    - group:            Clearwater_SOL_vellum_m2m1
      direction:        egress
      ethertype:        IPv4
      protocol:         tcp
      min:              4000
      max:              4000
      mode:             group
      remote_group:     Clearwater_SOL_bono_m2m1
    - group:            Clearwater_SOL_vellum_m2m1
      direction:        ingress
      ethertype:        IPv4
      protocol:         tcp
      min:              7253
      max:              7253
      mode:             group
      remote_group:     Clearwater_SOL_dime_m2m1
    - group:            Clearwater_SOL_vellum_m2m1
      direction:        ingress
      ethertype:        IPv4
      protocol:         tcp
      min:              9160
      max:              9160
      mode:             group
      remote_group:     Clearwater_SOL_dime_m2m1
    - group:            Clearwater_SOL_vellum_m2m1
      direction:        ingress
      ethertype:        IPv4
      protocol:         tcp
      min:              2380
      max:              2380
      mode:             group
      remote_group:     Clearwater_SOL_dime_m2m1
    - group:            Clearwater_SOL_vellum_m2m1
      direction:        ingress
      ethertype:        IPv4
      protocol:         tcp
      min:              4000
      max:              4000
      mode:             group
      remote_group:     Clearwater_SOL_dime_m2m1
    - group:            Clearwater_SOL_vellum_m2m1
      direction:        ingress
      ethertype:        IPv4
      protocol:         tcp
      min:              11311
      max:              11311
      mode:             group
      remote_group:     Clearwater_SOL_dime_m2m1
    - group:            Clearwater_SOL_vellum_m2m1
      direction:        ingress
      ethertype:        IPv4
      protocol:         tcp
      min:              7253
      max:              7253
      mode:             group
      remote_group:     Clearwater_SOL_homer_m2m1
    - group:            Clearwater_SOL_vellum_m2m1
      direction:        ingress
      ethertype:        IPv4
      protocol:         tcp
      min:              9160
      max:              9160
      mode:             group
      remote_group:     Clearwater_SOL_homer_m2m1
    - group:            Clearwater_SOL_vellum_m2m1
      direction:        ingress
      ethertype:        IPv4
      protocol:         tcp
      min:              2380
      max:              2380
      mode:             group
      remote_group:     Clearwater_SOL_homer_m2m1
    - group:            Clearwater_SOL_vellum_m2m1
      direction:        ingress
      ethertype:        IPv4
      protocol:         tcp
      min:              4000
      max:              4000
      mode:             group
      remote_group:     Clearwater_SOL_homer_m2m1
    - group:            Clearwater_SOL_vellum_m2m1
      direction:        ingress
      ethertype:        IPv4
      protocol:         tcp
      min:              2380
      max:              2380
      mode:             group
      remote_group:     Clearwater_SOL_ellis_m2m1
    - group:            Clearwater_SOL_vellum_m2m1
      direction:        ingress
      ethertype:        IPv4
      protocol:         tcp
      min:              4000
      max:              4000
      mode:             group
      remote_group:     Clearwater_SOL_ellis_m2m1
    - group:            Clearwater_SOL_vellum_m2m2
      direction:        egress
      ethertype:        IPv4
      protocol:         tcp
      min:              7253
      max:              7253
      mode:             group
      remote_group:     Clearwater_SOL_vellum_m2m2
    - group:            Clearwater_SOL_vellum_m2m2
      direction:        ingress
      ethertype:        IPv4
      protocol:         tcp
      min:              7253
      max:              7253
      mode:             group
      remote_group:     Clearwater_SOL_vellum_m2m2
    - group:            Clearwater_SOL_vellum_m2m2
      direction:        egress
      ethertype:        IPv4
      protocol:         tcp
      min:              11211
      max:              11211
      mode:             group
      remote_group:     Clearwater_SOL_vellum_m2m2
    - group:            Clearwater_SOL_vellum_m2m2
      direction:        ingress
      ethertype:        IPv4
      protocol:         tcp
      min:              11211
      max:              11211
      mode:             group
      remote_group:     Clearwater_SOL_vellum_m2m2
    - group:            Clearwater_SOL_vellum_m2m2
      direction:        egress
      ethertype:        IPv4
      protocol:         tcp
      min:              7000
      max:              7000
      mode:             group
      remote_group:     Clearwater_SOL_vellum_m2m2
    - group:            Clearwater_SOL_vellum_m2m2
      direction:        ingress
      ethertype:        IPv4
      protocol:         tcp
      min:              7000
      max:              7000
      mode:             group
      remote_group:     Clearwater_SOL_vellum_m2m2
    - group:            Clearwater_SOL_dime_oam
      direction:        ingress
      ethertype:        IPv4
      protocol:         tcp
      min:              22
      max:              22
      mode:             group
      remote_group:     Clearwater_SOL_jumphost_oam
    - group:            Clearwater_SOL_dime_m2m1
      direction:        ingress
      ethertype:        IPv4
      protocol:         tcp
      min:              8888
      max:              8888
      mode:             group
      remote_group:     Clearwater_SOL_bono_m2m1
    - group:            Clearwater_SOL_dime_m2m1
      direction:        ingress
      ethertype:        IPv4
      protocol:         tcp
      min:              10888
      max:              10888
      mode:             group
      remote_group:     Clearwater_SOL_bono_m2m1
    - group:            Clearwater_SOL_dime_m2m1
      direction:        ingress
      ethertype:        IPv4
      protocol:         tcp
      min:              2380
      max:              2380
      mode:             group
      remote_group:     Clearwater_SOL_bono_m2m1
    - group:            Clearwater_SOL_dime_m2m1
      direction:        ingress
      ethertype:        IPv4
      protocol:         tcp
      min:              4000
      max:              4000
      mode:             group
      remote_group:     Clearwater_SOL_bono_m2m1
    - group:            Clearwater_SOL_dime_m2m1
      direction:        ingress
      ethertype:        IPv4
      protocol:         tcp
      min:              8888
      max:              8888
      mode:             group
      remote_group:     Clearwater_SOL_sprout_m2m1
    - group:            Clearwater_SOL_dime_m2m1
      direction:        ingress
      ethertype:        IPv4
      protocol:         tcp
      min:              10888
      max:              10888
      mode:             group
      remote_group:     Clearwater_SOL_sprout_m2m1
    - group:            Clearwater_SOL_dime_m2m1
      direction:        ingress
      ethertype:        IPv4
      protocol:         tcp
      min:              2380
      max:              2380
      mode:             group
      remote_group:     Clearwater_SOL_sprout_m2m1
    - group:            Clearwater_SOL_dime_m2m1
      direction:        ingress
      ethertype:        IPv4
      protocol:         tcp
      min:              4000
      max:              4000
      mode:             group
      remote_group:     Clearwater_SOL_sprout_m2m1
    - group:            Clearwater_SOL_dime_m2m1
      direction:        ingress
      ethertype:        IPv4
      protocol:         tcp
      min:              8888
      max:              8888
      mode:             group
      remote_group:     Clearwater_SOL_vellum_m2m1
    - group:            Clearwater_SOL_dime_m2m1
      direction:        ingress
      ethertype:        IPv4
      protocol:         tcp
      min:              10888
      max:              10888
      mode:             group
      remote_group:     Clearwater_SOL_vellum_m2m1
    - group:            Clearwater_SOL_dime_m2m1
      direction:        ingress
      ethertype:        IPv4
      protocol:         tcp
      min:              2380
      max:              2380
      mode:             group
      remote_group:     Clearwater_SOL_vellum_m2m1
    - group:            Clearwater_SOL_dime_m2m1
      direction:        ingress
      ethertype:        IPv4
      protocol:         tcp
      min:              4000
      max:              4000
      mode:             group
      remote_group:     Clearwater_SOL_vellum_m2m1
    - group:            Clearwater_SOL_dime_m2m1
      direction:        egress
      ethertype:        IPv4
      protocol:         tcp
      min:              3128
      max:              3128
      mode:             group
      remote_group:     Clearwater_SOL_proxy_m2m1
    - group:            Clearwater_SOL_dime_m2m1
      direction:        egress
      ethertype:        IPv4
      protocol:         tcp
      min:              9888
      max:              9888
      mode:             group
      remote_group:     Clearwater_SOL_sprout_m2m1
    - group:            Clearwater_SOL_dime_m2m1
      direction:        egress
      ethertype:        IPv4
      protocol:         tcp
      min:              7253
      max:              7253
      mode:             group
      remote_group:     Clearwater_SOL_vellum_m2m1
    - group:            Clearwater_SOL_dime_m2m1
      direction:        egress
      ethertype:        IPv4
      protocol:         tcp
      min:              9160
      max:              9160
      mode:             group
      remote_group:     Clearwater_SOL_vellum_m2m1
    - group:            Clearwater_SOL_dime_m2m1
      direction:        egress
      ethertype:        IPv4
      protocol:         tcp
      min:              7888
      max:              7888
      mode:             group
      remote_group:     Clearwater_SOL_homer_m2m1
    - group:            Clearwater_SOL_dime_m2m1
      direction:        egress
      ethertype:        IPv4
      protocol:         udp
      min:              53
      max:              53
      mode:             group
      remote_group:     Clearwater_SOL_proxy_m2m1
    - group:            Clearwater_SOL_dime_m2m1
      direction:        egress
      ethertype:        IPv4
      protocol:         tcp
      min:              2380
      max:              2380
      mode:             group
      remote_group:     Clearwater_SOL_ellis_m2m1
    - group:            Clearwater_SOL_dime_m2m1
      direction:        egress
      ethertype:        IPv4
      protocol:         tcp
      min:              4000
      max:              4000
      mode:             group
      remote_group:     Clearwater_SOL_ellis_m2m1
    - group:            Clearwater_SOL_dime_m2m1
      direction:        egress
      ethertype:        IPv4
      protocol:         tcp
      min:              2380
      max:              2380
      mode:             group
      remote_group:     Clearwater_SOL_sprout_m2m1
    - group:            Clearwater_SOL_dime_m2m1
      direction:        egress
      ethertype:        IPv4
      protocol:         tcp
      min:              4000
      max:              4000
      mode:             group
      remote_group:     Clearwater_SOL_sprout_m2m1
    - group:            Clearwater_SOL_dime_m2m1
      direction:        egress
      ethertype:        IPv4
      protocol:         tcp
      min:              2380
      max:              2380
      mode:             group
      remote_group:     Clearwater_SOL_homer_m2m1
    - group:            Clearwater_SOL_dime_m2m1
      direction:        egress
      ethertype:        IPv4
      protocol:         tcp
      min:              4000
      max:              4000
      mode:             group
      remote_group:     Clearwater_SOL_homer_m2m1
    - group:            Clearwater_SOL_dime_m2m1
      direction:        egress
      ethertype:        IPv4
      protocol:         tcp
      min:              2380
      max:              2380
      mode:             group
      remote_group:     Clearwater_SOL_bono_m2m1
    - group:            Clearwater_SOL_dime_m2m1
      direction:        egress
      ethertype:        IPv4
      protocol:         tcp
      min:              4000
      max:              4000
      mode:             group
      remote_group:     Clearwater_SOL_bono_m2m1
    - group:            Clearwater_SOL_dime_m2m1
      direction:        egress
      ethertype:        IPv4
      protocol:         tcp
      min:              2380
      max:              2380
      mode:             group
      remote_group:     Clearwater_SOL_vellum_m2m1
    - group:            Clearwater_SOL_dime_m2m1
      direction:        egress
      ethertype:        IPv4
      protocol:         tcp
      min:              4000
      max:              4000
      mode:             group
      remote_group:     Clearwater_SOL_vellum_m2m1
    - group:            Clearwater_SOL_dime_m2m1
      direction:        egress
      ethertype:        IPv4
      protocol:         tcp
      min:              11311
      max:              11311
      mode:             group
      remote_group:     Clearwater_SOL_vellum_m2m1
    - group:            Clearwater_SOL_dime_m2m1
      direction:        ingress
      ethertype:        IPv4
      protocol:         tcp
      min:              2380
      max:              2380
      mode:             group
      remote_group:     Clearwater_SOL_homer_m2m1
    - group:            Clearwater_SOL_dime_m2m1
      direction:        ingress
      ethertype:        IPv4
      protocol:         tcp
      min:              4000
      max:              4000
      mode:             group
      remote_group:     Clearwater_SOL_homer_m2m1
    - group:            Clearwater_SOL_dime_m2m1
      direction:        ingress
      ethertype:        IPv4
      protocol:         tcp
      min:              8889
      max:              8889
      mode:             group
      remote_group:     Clearwater_SOL_ellis_m2m1
    - group:            Clearwater_SOL_dime_m2m1
      direction:        ingress
      ethertype:        IPv4
      protocol:         tcp
      min:              2380
      max:              2380
      mode:             group
      remote_group:     Clearwater_SOL_ellis_m2m1
    - group:            Clearwater_SOL_dime_m2m1
      direction:        ingress
      ethertype:        IPv4
      protocol:         tcp
      min:              4000
      max:              4000
      mode:             group
      remote_group:     Clearwater_SOL_ellis_m2m1
    - group:            Clearwater_SOL_homer_oam
      direction:        ingress
      ethertype:        IPv4
      protocol:         tcp
      min:              22
      max:              22
      mode:             group
      remote_group:     Clearwater_SOL_jumphost_oam
    - group:            Clearwater_SOL_homer_m2m1
      direction:        ingress
      ethertype:        IPv4
      protocol:         tcp
      min:              2380
      max:              2380
      mode:             group
      remote_group:     Clearwater_SOL_bono_m2m1
    - group:            Clearwater_SOL_homer_m2m1
      direction:        ingress
      ethertype:        IPv4
      protocol:         tcp
      min:              4000
      max:              4000
      mode:             group
      remote_group:     Clearwater_SOL_bono_m2m1
    - group:            Clearwater_SOL_homer_m2m1
      direction:        ingress
      ethertype:        IPv4
      protocol:         tcp
      min:              7888
      max:              7888
      mode:             group
      remote_group:     Clearwater_SOL_sprout_m2m1
    - group:            Clearwater_SOL_homer_m2m1
      direction:        ingress
      ethertype:        IPv4
      protocol:         tcp
      min:              2380
      max:              2380
      mode:             group
      remote_group:     Clearwater_SOL_sprout_m2m1
    - group:            Clearwater_SOL_homer_m2m1
      direction:        ingress
      ethertype:        IPv4
      protocol:         tcp
      min:              4000
      max:              4000
      mode:             group
      remote_group:     Clearwater_SOL_sprout_m2m1
    - group:            Clearwater_SOL_homer_m2m1
      direction:        ingress
      ethertype:        IPv4
      protocol:         tcp
      min:              2380
      max:              2380
      mode:             group
      remote_group:     Clearwater_SOL_vellum_m2m1
    - group:            Clearwater_SOL_homer_m2m1
      direction:        ingress
      ethertype:        IPv4
      protocol:         tcp
      min:              4000
      max:              4000
      mode:             group
      remote_group:     Clearwater_SOL_vellum_m2m1
    - group:            Clearwater_SOL_homer_m2m1
      direction:        ingress
      ethertype:        IPv4
      protocol:         tcp
      min:              7888
      max:              7888
      mode:             group
      remote_group:     Clearwater_SOL_dime_m2m1
    - group:            Clearwater_SOL_homer_m2m1
      direction:        ingress
      ethertype:        IPv4
      protocol:         tcp
      min:              2380
      max:              2380
      mode:             group
      remote_group:     Clearwater_SOL_dime_m2m1
    - group:            Clearwater_SOL_homer_m2m1
      direction:        ingress
      ethertype:        IPv4
      protocol:         tcp
      min:              4000
      max:              4000
      mode:             group
      remote_group:     Clearwater_SOL_dime_m2m1
    - group:            Clearwater_SOL_homer_m2m1
      direction:        egress
      ethertype:        IPv4
      protocol:         tcp
      min:              3128
      max:              3128
      mode:             group
      remote_group:     Clearwater_SOL_proxy_m2m1
    - group:            Clearwater_SOL_homer_m2m1
      direction:        egress
      ethertype:        IPv4
      protocol:         tcp
      min:              7253
      max:              7253
      mode:             group
      remote_group:     Clearwater_SOL_vellum_m2m1
    - group:            Clearwater_SOL_homer_m2m1
      direction:        egress
      ethertype:        IPv4
      protocol:         tcp
      min:              9160
      max:              9160
      mode:             group
      remote_group:     Clearwater_SOL_vellum_m2m1
    - group:            Clearwater_SOL_homer_m2m1
      direction:        egress
      ethertype:        IPv4
      protocol:         udp
      min:              53
      max:              53
      mode:             group
      remote_group:     Clearwater_SOL_proxy_m2m1
    - group:            Clearwater_SOL_homer_m2m1
      direction:        egress
      ethertype:        IPv4
      protocol:         tcp
      min:              2380
      max:              2380
      mode:             group
      remote_group:     Clearwater_SOL_ellis_m2m1
    - group:            Clearwater_SOL_homer_m2m1
      direction:        egress
      ethertype:        IPv4
      protocol:         tcp
      min:              4000
      max:              4000
      mode:             group
      remote_group:     Clearwater_SOL_ellis_m2m1
    - group:            Clearwater_SOL_homer_m2m1
      direction:        egress
      ethertype:        IPv4
      protocol:         tcp
      min:              2380
      max:              2380
      mode:             group
      remote_group:     Clearwater_SOL_sprout_m2m1
    - group:            Clearwater_SOL_homer_m2m1
      direction:        egress
      ethertype:        IPv4
      protocol:         tcp
      min:              4000
      max:              4000
      mode:             group
      remote_group:     Clearwater_SOL_sprout_m2m1
    - group:            Clearwater_SOL_homer_m2m1
      direction:        egress
      ethertype:        IPv4
      protocol:         tcp
      min:              2380
      max:              2380
      mode:             group
      remote_group:     Clearwater_SOL_bono_m2m1
    - group:            Clearwater_SOL_homer_m2m1
      direction:        egress
      ethertype:        IPv4
      protocol:         tcp
      min:              4000
      max:              4000
      mode:             group
      remote_group:     Clearwater_SOL_bono_m2m1
    - group:            Clearwater_SOL_homer_m2m1
      direction:        egress
      ethertype:        IPv4
      protocol:         tcp
      min:              2380
      max:              2380
      mode:             group
      remote_group:     Clearwater_SOL_dime_m2m1
    - group:            Clearwater_SOL_homer_m2m1
      direction:        egress
      ethertype:        IPv4
      protocol:         tcp
      min:              4000
      max:              4000
      mode:             group
      remote_group:     Clearwater_SOL_dime_m2m1
    - group:            Clearwater_SOL_homer_m2m1
      direction:        egress
      ethertype:        IPv4
      protocol:         tcp
      min:              2380
      max:              2380
      mode:             group
      remote_group:     Clearwater_SOL_vellum_m2m1
    - group:            Clearwater_SOL_homer_m2m1
      direction:        egress
      ethertype:        IPv4
      protocol:         tcp
      min:              4000
      max:              4000
      mode:             group
      remote_group:     Clearwater_SOL_vellum_m2m1
    - group:            Clearwater_SOL_homer_m2m1
      direction:        ingress
      ethertype:        IPv4
      protocol:         tcp
      min:              7888
      max:              7888
      mode:             group
      remote_group:     Clearwater_SOL_ellis_m2m1
    - group:            Clearwater_SOL_homer_m2m1
      direction:        ingress
      ethertype:        IPv4
      protocol:         tcp
      min:              2380
      max:              2380
      mode:             group
      remote_group:     Clearwater_SOL_ellis_m2m1
    - group:            Clearwater_SOL_homer_m2m1
      direction:        ingress
      ethertype:        IPv4
      protocol:         tcp
      min:              4000
      max:              4000
      mode:             group
      remote_group:     Clearwater_SOL_ellis_m2m1
    - group:            Clearwater_SOL_ellis_oam
      direction:        ingress
      ethertype:        IPv4
      protocol:         tcp
      min:              22
      max:              22
      mode:             group
      remote_group:     Clearwater_SOL_jumphost_oam
    - group:            Clearwater_SOL_ellis_oam
      direction:        ingress
      ethertype:        IPv4
      protocol:         tcp
      min:              80
      max:              80
      mode:             group
      remote_group:     Clearwater_SOL_jumphost_oam
    - group:            Clearwater_SOL_ellis_oam
      direction:        ingress
      ethertype:        IPv4
      protocol:         tcp
      min:              443
      max:              443
      mode:             group
      remote_group:     Clearwater_SOL_jumphost_oam
    - group:            Clearwater_SOL_ellis_m2m1
      direction:        ingress
      ethertype:        IPv4
      protocol:         tcp
      min:              2380
      max:              2380
      mode:             group
      remote_group:     Clearwater_SOL_bono_m2m1
    - group:            Clearwater_SOL_ellis_m2m1
      direction:        ingress
      ethertype:        IPv4
      protocol:         tcp
      min:              4000
      max:              4000
      mode:             group
      remote_group:     Clearwater_SOL_bono_m2m1
    - group:            Clearwater_SOL_ellis_m2m1
      direction:        ingress
      ethertype:        IPv4
      protocol:         tcp
      min:              2380
      max:              2380
      mode:             group
      remote_group:     Clearwater_SOL_sprout_m2m1
    - group:            Clearwater_SOL_ellis_m2m1
      direction:        ingress
      ethertype:        IPv4
      protocol:         tcp
      min:              4000
      max:              4000
      mode:             group
      remote_group:     Clearwater_SOL_sprout_m2m1
    - group:            Clearwater_SOL_ellis_m2m1
      direction:        ingress
      ethertype:        IPv4
      protocol:         tcp
      min:              2380
      max:              2380
      mode:             group
      remote_group:     Clearwater_SOL_vellum_m2m1
    - group:            Clearwater_SOL_ellis_m2m1
      direction:        ingress
      ethertype:        IPv4
      protocol:         tcp
      min:              4000
      max:              4000
      mode:             group
      remote_group:     Clearwater_SOL_vellum_m2m1
    - group:            Clearwater_SOL_ellis_m2m1
      direction:        ingress
      ethertype:        IPv4
      protocol:         tcp
      min:              2380
      max:              2380
      mode:             group
      remote_group:     Clearwater_SOL_dime_m2m1
    - group:            Clearwater_SOL_ellis_m2m1
      direction:        ingress
      ethertype:        IPv4
      protocol:         tcp
      min:              4000
      max:              4000
      mode:             group
      remote_group:     Clearwater_SOL_dime_m2m1
    - group:            Clearwater_SOL_ellis_m2m1
      direction:        ingress
      ethertype:        IPv4
      protocol:         tcp
      min:              2380
      max:              2380
      mode:             group
      remote_group:     Clearwater_SOL_homer_m2m1
    - group:            Clearwater_SOL_ellis_m2m1
      direction:        ingress
      ethertype:        IPv4
      protocol:         tcp
      min:              4000
      max:              4000
      mode:             group
      remote_group:     Clearwater_SOL_homer_m2m1
    - group:            Clearwater_SOL_ellis_m2m1
      direction:        egress
      ethertype:        IPv4
      protocol:         tcp
      min:              3128
      max:              3128
      mode:             group
      remote_group:     Clearwater_SOL_proxy_m2m1
    - group:            Clearwater_SOL_ellis_m2m1
      direction:        egress
      ethertype:        IPv4
      protocol:         tcp
      min:              8889
      max:              8889
      mode:             group
      remote_group:     Clearwater_SOL_dime_m2m1
    - group:            Clearwater_SOL_ellis_m2m1
      direction:        egress
      ethertype:        IPv4
      protocol:         tcp
      min:              7888
      max:              7888
      mode:             group
      remote_group:     Clearwater_SOL_homer_m2m1
    - group:            Clearwater_SOL_ellis_m2m1
      direction:        egress
      ethertype:        IPv4
      protocol:         udp
      min:              53
      max:              53
      mode:             group
      remote_group:     Clearwater_SOL_proxy_m2m1
    - group:            Clearwater_SOL_ellis_m2m1
      direction:        egress
      ethertype:        IPv4
      protocol:         tcp
      min:              2380
      max:              2380
      mode:             group
      remote_group:     Clearwater_SOL_bono_m2m1
    - group:            Clearwater_SOL_ellis_m2m1
      direction:        egress
      ethertype:        IPv4
      protocol:         tcp
      min:              4000
      max:              4000
      mode:             group
      remote_group:     Clearwater_SOL_bono_m2m1
    - group:            Clearwater_SOL_ellis_m2m1
      direction:        egress
      ethertype:        IPv4
      protocol:         tcp
      min:              2380
      max:              2380
      mode:             group
      remote_group:     Clearwater_SOL_sprout_m2m1
    - group:            Clearwater_SOL_ellis_m2m1
      direction:        egress
      ethertype:        IPv4
      protocol:         tcp
      min:              4000
      max:              4000
      mode:             group
      remote_group:     Clearwater_SOL_sprout_m2m1
    - group:            Clearwater_SOL_ellis_m2m1
      direction:        egress
      ethertype:        IPv4
      protocol:         tcp
      min:              2380
      max:              2380
      mode:             group
      remote_group:     Clearwater_SOL_homer_m2m1
    - group:            Clearwater_SOL_ellis_m2m1
      direction:        egress
      ethertype:        IPv4
      protocol:         tcp
      min:              4000
      max:              4000
      mode:             group
      remote_group:     Clearwater_SOL_homer_m2m1
    - group:            Clearwater_SOL_ellis_m2m1
      direction:        egress
      ethertype:        IPv4
      protocol:         tcp
      min:              2380
      max:              2380
      mode:             group
      remote_group:     Clearwater_SOL_dime_m2m1
    - group:            Clearwater_SOL_ellis_m2m1
      direction:        egress
      ethertype:        IPv4
      protocol:         tcp
      min:              4000
      max:              4000
      mode:             group
      remote_group:     Clearwater_SOL_dime_m2m1
    - group:            Clearwater_SOL_ellis_m2m1
      direction:        egress
      ethertype:        IPv4
      protocol:         tcp
      min:              2380
      max:              2380
      mode:             group
      remote_group:     Clearwater_SOL_vellum_m2m1
    - group:            Clearwater_SOL_ellis_m2m1
      direction:        egress
      ethertype:        IPv4
      protocol:         tcp
      min:              4000
      max:              4000
      mode:             group
      remote_group:     Clearwater_SOL_vellum_m2m1

    networks:
    - name: Clearwater_SOL_svc2
      ipv4:
        cidr:  "198.18.212.128/28"
    - name: Clearwater_SOL_svc1
      ipv4:
        cidr:  "198.18.212.144/28"
    - name: Clearwater_SOL_oam
      ipv4:
        cidr:  "192.168.0.1/24"
    - name: Clearwater_SOL_m2m1
      ipv4:
        cidr:  "192.168.1.1/24"
    - name: Clearwater_SOL_m2m2
      ipv4:
        cidr:  "192.168.2.1/24"

    ports:
    - name:           Clearwater_SOL_jumphost_0_svc2
      network:        Clearwater_SOL_svc2
      security_group: Clearwater_SOL_jumphost_svc2
    - name:           Clearwater_SOL_jumphost_0_oam
      network:        Clearwater_SOL_oam
      security_group: Clearwater_SOL_jumphost_oam
    - name:           Clearwater_SOL_proxy_0_oam
      network:        Clearwater_SOL_oam
      security_group: Clearwater_SOL_proxy_oam
    - name:           Clearwater_SOL_proxy_0_m2m1
      network:        Clearwater_SOL_m2m1
      security_group: Clearwater_SOL_proxy_m2m1
    - name:           Clearwater_SOL_proxy_0_svc1
      network:        Clearwater_SOL_svc1
      security_group: Clearwater_SOL_proxy_svc1
    - name:           Clearwater_SOL_bono_0_oam
      network:        Clearwater_SOL_oam
      security_group: Clearwater_SOL_bono_oam
    - name:           Clearwater_SOL_bono_0_m2m1
      network:        Clearwater_SOL_m2m1
      security_group: Clearwater_SOL_bono_m2m1
    - name:           Clearwater_SOL_bono_0_svc1
      network:        Clearwater_SOL_svc1
      security_group: Clearwater_SOL_bono_svc1
    - name:           Clearwater_SOL_sprout_0_oam
      network:        Clearwater_SOL_oam
      security_group: Clearwater_SOL_sprout_oam
    - name:           Clearwater_SOL_sprout_0_m2m1
      network:        Clearwater_SOL_m2m1
      security_group: Clearwater_SOL_sprout_m2m1
    - name:           Clearwater_SOL_vellum_0_oam
      network:        Clearwater_SOL_oam
      security_group: Clearwater_SOL_vellum_oam
    - name:           Clearwater_SOL_vellum_0_m2m1
      network:        Clearwater_SOL_m2m1
      security_group: Clearwater_SOL_vellum_m2m1
    - name:           Clearwater_SOL_vellum_0_m2m2
      network:        Clearwater_SOL_m2m2
      security_group: Clearwater_SOL_vellum_m2m2
    - name:           Clearwater_SOL_dime_0_oam
      network:        Clearwater_SOL_oam
      security_group: Clearwater_SOL_dime_oam
    - name:           Clearwater_SOL_dime_0_m2m1
      network:        Clearwater_SOL_m2m1
      security_group: Clearwater_SOL_dime_m2m1
    - name:           Clearwater_SOL_homer_0_oam
      network:        Clearwater_SOL_oam
      security_group: Clearwater_SOL_homer_oam
    - name:           Clearwater_SOL_homer_0_m2m1
      network:        Clearwater_SOL_m2m1
      security_group: Clearwater_SOL_homer_m2m1
    - name:           Clearwater_SOL_ellis_0_oam
      network:        Clearwater_SOL_oam
      security_group: Clearwater_SOL_ellis_oam
    - name:           Clearwater_SOL_ellis_0_m2m1
      network:        Clearwater_SOL_m2m1
      security_group: Clearwater_SOL_ellis_m2m1

    nodes:
    - name:              Clearwater_SOL_jumphost_0
      availability_zone: MGMT
      flavor:            m1.small
      image:             ubuntu-16.04.1-x86_64
      key_name:          Clearwater_SOL_keypair
      nics:
          - port-name: Clearwater_SOL_jumphost_0_svc2
          - port-name: Clearwater_SOL_jumphost_0_oam
    - name:              Clearwater_SOL_proxy_0
      availability_zone: MGMT
      flavor:            m1.small
      image:             ubuntu-16.04.1-x86_64
      key_name:          Clearwater_SOL_keypair
      nics:
          - port-name: Clearwater_SOL_proxy_0_oam
          - port-name: Clearwater_SOL_proxy_0_m2m1
          - port-name: Clearwater_SOL_proxy_0_svc1
    - name:              Clearwater_SOL_bono_0
      availability_zone: EXT
      flavor:            m1.small
      image:             ubuntu-14.04.5-x86_64
      key_name:          Clearwater_SOL_keypair
      nics:
          - port-name: Clearwater_SOL_bono_0_oam
          - port-name: Clearwater_SOL_bono_0_m2m1
          - port-name: Clearwater_SOL_bono_0_svc1
    - name:              Clearwater_SOL_sprout_0
      availability_zone: INT
      flavor:            m1.small
      image:             ubuntu-14.04.5-x86_64
      key_name:          Clearwater_SOL_keypair
      nics:
          - port-name: Clearwater_SOL_sprout_0_oam
          - port-name: Clearwater_SOL_sprout_0_m2m1
    - name:              Clearwater_SOL_vellum_0
      availability_zone: INT
      flavor:            m1.small
      image:             ubuntu-14.04.5-x86_64
      key_name:          Clearwater_SOL_keypair
      nics:
          - port-name: Clearwater_SOL_vellum_0_oam
          - port-name: Clearwater_SOL_vellum_0_m2m1
          - port-name: Clearwater_SOL_vellum_0_m2m2
    - name:              Clearwater_SOL_dime_0
      availability_zone: INT
      flavor:            m1.small
      image:             ubuntu-14.04.5-x86_64
      key_name:          Clearwater_SOL_keypair
      nics:
          - port-name: Clearwater_SOL_dime_0_oam
          - port-name: Clearwater_SOL_dime_0_m2m1
    - name:              Clearwater_SOL_homer_0
      availability_zone: INT
      flavor:            m1.small
      image:             ubuntu-14.04.5-x86_64
      key_name:          Clearwater_SOL_keypair
      nics:
          - port-name: Clearwater_SOL_homer_0_oam
          - port-name: Clearwater_SOL_homer_0_m2m1
    - name:              Clearwater_SOL_ellis_0
      availability_zone: INT
      flavor:            m1.small
      image:             ubuntu-14.04.5-x86_64
      key_name:          Clearwater_SOL_keypair
      nics:
          - port-name: Clearwater_SOL_ellis_0_oam
          - port-name: Clearwater_SOL_ellis_0_m2m1

    volumes:
        - name:        Clearwater_SOL_ellis_0_data
          server:      Clearwater_SOL_ellis_0
          volume_type: INT
          size:        20
          device:      /dev/vdb
