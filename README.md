# DCQCN-validation
## Topology and traffic pattern
The same as Fig.1 in the paper. H1 and H2 send large messages with a size of 20MB, forming long-lived flow F1, F2 to R1 and R2, respectively. After 3ms, H3-H17 start sending small messages to R2 at the same time, lasting for 1ms. The size of each message is 4KB.
<div align="center"><img width="400" height="200" src="https://github.com/sc20anonymous/DCQCN-validation/raw/master/topology.png"/></div>

## Simulator 
ns3, using code released by the author of DCQCN.

DCQCN parameters:
Parameter|Value
|--|:--:|
|Kmin|10KB|
|Kmax|100KB|
|Pmax|0.01|
|Timer|50us|
|Byte Counter|10MB|
|g|1/256|

## Results
