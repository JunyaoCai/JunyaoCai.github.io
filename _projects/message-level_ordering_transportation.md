---
title: "Message-level Ordering Transportation"
collection: projects
permalink: /projects/message-level_ordering_transportation
excerpt: 'A Connection-oriented message-level Ordering Transportation Method.'
# excerpt: "Short description of portfolio item number 1<br/><img src='/images/500x300.png'>"
---
## Motivation
1. Connection-level transmission control requires that different messages must be delivered in order, resulting in head-of-line blocking;
2. The connection-level transmission control usually needs to cooperate with the flow-by-flow ECMP strategy, so as to minimize the disorder degree when the data packets arrive at the receiving end. This coarse-grained load balancing strategy reduces network utilization;
3. Datagram-level transmission control cannot guarantee the reliability of data transmission and the in-order delivery of different packets within the same message.

> The operation rate of Mellanox CX5 declines when concurrent connnection scales.
<img class="img-responsive" src="/images/projects/Message/Message.png">

## Overview
Based on the problems existing in the existing RDMA transmission control scheme, we propose an RDMA transmission control method with message-level ordering. Strict priority between messages is often unnecessary, and the introduction of sequence control between messages can easily lead to head-of-line blocking, and also indirectly reduce network resource utilization. In fact, what needs to be strictly guaranteed is the order between different packets within a message. This solution realizes reliable transmission at the message level and the sequential delivery of data packets in the message, which greatly alleviates the problem of head-of-line blocking, improves the load balancing effect, and reduces the complexity of application development.