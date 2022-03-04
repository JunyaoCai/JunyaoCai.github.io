---
title: "Smart Flow Table Compression"
collection: projects
permalink: /projects/smart_flow_table_compression
excerpt: 'An exploration of AI for flow table compression.'
# excerpt: "Short description of portfolio item number 1<br/><img src='/images/500x300.png'>"
---
## Summary
Multi-field packet classification is a crucial component in modern software-defined data center networks. To achieve high throughput and low latency, state-of-the-art algorithms strive to fit the rule lookup data structures into on-die caches; however, they do not scale well with the number of rules.
We present a novel approach, which uses nerual network instead of traditional data structure.
- Introduces the prior knowledge of "mask length" to the neural network, does not require its own learning, and does not generate other additional overhead
- When the rules are updated, only the neural network corresponding to the tuple needs to be retrained. Since the size of a single neural network is small, it can support fast incremental update
- The process of package inference can be parallelized, which speeds up package inference

<img class="img-responsive" src="/images/projects/NN_Flow_Table/nn_flow_table.png">