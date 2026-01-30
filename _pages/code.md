---
layout: archive
title: "Code"
permalink: /code/
author_profile: true
---

Here you find source code and datasets created as part of my research. You can also find these resources on [my GitHub page](https://github.com/jonadmark).

## [IntSight: Diagnosing SLO Violations with In-band Network Telemetry](https://github.com/jonadmark/intsight-conext)
<span style="color:grey;">Dec, 2020</span> • The 16th ACM International Conference on emerging Networking EXperiments and Technologies (CoNEXT'20)

[![An overview of IntSight](/images/intsight-overview.png)](https://github.com/jonadmark/intsight-conext)

Performance requirements for many of today's high-perfor-mance networks are expressed as service-level objectives (SLOs), i.e., precise guarantees, typically on latency and bandwidth, that a user can expect from the network. For network operators, monitoring their own SLO compliance, and quickly diagnosing any violations, is a critical element for effective operations. Unfortunately, existing network architectures are not engineered for this purpose; there is no mechanism, for example, for the operator to monitor the 95th per-centile latency experienced by a customer. Data plane programmability has made per-packet measurements possible but brings the challenge of keeping the monitoring overhead low and practical. In this paper, we present IntSight, a system for highly accurate and fine-grained detection and diagnosis of SLO violations. The main contribution of IntSight is, building upon in-band telemetry, introducing path-wise computation of network metrics and selective generation of reports. We show the effectiveness of IntSight by way of two use cases. Our evaluation using real networks also shows that IntSight generates up to two orders of magnitude less monitoring traffic than state-of-the-art approaches. Furthermore, its processing and memory requirements are low and therefore compatible with currently existing programmable platforms.

[Click here to access the code for IntSight's prototype and experiments](https://github.com/jonadmark/intsight-conext). Use the following link to access the [full paper](https://dl.acm.org/doi/abs/10.1145/3386367.3431306) and the [recorded presentation](https://www.youtube.com/watch?v=1KA6CJ7qqSU).