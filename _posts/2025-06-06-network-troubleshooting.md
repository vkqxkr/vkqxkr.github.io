---
title: Network Troubleshooting
description: >-
  CKA with Practice Tests 강의 Network Troubleshooting 요약
author: jinhyouk park
date: 2025-06-06 12:00:00 +0900
categories: [DevOps, Kubernetes]
tags: [Certificate, CKA, Kubernetes]
---


쿠버네티스는 다양한 CNI(Container Network Interface)를 지원한다.

아래는 대표적인 3가지이다.

| 플러그인    | 설치 명령어                                                                                                                                        | 특징                |
| --------- | ----------------------------------------------------------------------------------------------------------------------------------------------- | ----------------- |
| Weave Net | ```kubectl apply -f https://github.com/weaveworks/weave/releases/download/v2.8.1/weave-daemonset-k8s.yaml```                                    | -                 |
| Flannel   | ```kubectl apply -f https://raw.githubusercontent.com/coreos/flannel/2140ac876ef134e0ed5af15c65e414cf26827915/Documentation/kube-flannel.yml``` | NetworkPolicy **미지원** |
| Calico    | ```curl https://raw.githubusercontent.com/projectcalico/calico/v3.25.0/manifests/calico.yaml \| kubectl apply -f -```                           | NetworkPolicy **지원**  |

여러 개의 CNI 설정 파일이 있을 경우 kubelet은 /etc/cni/net.d/에서 사전순으로 가장 이름이 먼저 나오는 CNI 설정 파일을 사용한다.

```yaml
    Command:
      /usr/local/bin/kube-proxy
      --config=/var/lib/kube-proxy/config.conf
      --hostname-override=$(NODE_NAME)
```

```kube-proxy``` 와 관련된 문제를 해결하는 방법은 아래와 같다.
1. kube-proxy 파드의 상태를 확인한다.
2. kube-proxy 로그를 확인한다.
3. configmap을 확인한다.
