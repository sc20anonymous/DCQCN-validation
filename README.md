# DCQCN-validation
## Topology and traffic pattern
The same as Fig.1 in the paper. H1 and H2 send large messages with a size of 20MB, forming long-lived flow F1, F2 to R1 and R2, respectively. After 3ms, H3-H17 start sending small messages to R2 at the same time, lasting for 1ms. The size of each small message is 4KB.
<div align="center"><img width="400" height="200" src="https://github.com/sc20anonymous/DCQCN-validation/raw/master/topology.png"/></div>

## Simulator 
ns3, code released by the author of DCQCN.

DCQCN parameters:
Parameter|Value
|--|:--:|
|Kmin|5KB|
|Kmax|100KB|
|Pmax|0.01|
|Timer|50us|
|Byte Counter|10MB|
|g|1/256|

## Results
### Overall throughput of F1 and F2. 

The under-utilization time of link P2-P1 is 16ms.
<div align="center"><img width="400" height="280" src="https://github.com/sc20anonymous/DCQCN-validation/raw/master/dcqcn_overall_throughput.png"/></div>

### Sending rate of F1. 

CC rate refers to the sending rate regulated by DCQCN. Real rate refers to final sending rate regulated by both PFC and DCQCN.
- Congestion detection without considering PFC backpressure: CC rate of F1 is improperly reduced to about 9Gbps.
- The sluggish rate adjustment of end-to-end CC mismatches the fast hop-by-hop PFC: PFC dominates sending rate for about 1.2ms after burst launching at 3ms.
<div align="center"><img width="400" height="280" src="https://github.com/sc20anonymous/DCQCN-validation/raw/master/dcqcn_cc_rate.png"/></div>
