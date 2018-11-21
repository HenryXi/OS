# Relative time in computer
In this book [Systems Performance: Enterprise and the Cloud](https://www.amazon.com/Systems-Performance-Enterprise-Brendan-Gregg/dp/0133390098/ref=sr_1_1?ie=UTF8&qid=1542768058&sr=8-1&keywords=Systems+Performance%3A+Enterprise+and+the+Cloud)
author make a single CPU cycle equivalent to one second to make us feel how fast CPU is. 

| event | Actual Latency | Scaled Latency |
| :------ | :------ | :------ |
| One CPU cycle | 0.3ns | 1s |
| Level 1 cache access | 0.9ns | 3s |
| Level 2 cache access | 2.8ns | 9s |
| Level 3 cache access | 12.9ns | 43s |
| Main memory access (DDR DIMM) | 120ns | 6min |
| SSD I/O | 50~150us | 2~6days |
| Rotational disk I/O | 1-10ms | 1~12month |
| Internet call: San Francisco to New York City | 40ms | 4years |
| TCP packet retransmission | 1~3s | 105~317years |
| OS virtualization restart | 40s | 4,000years |
| Physical system restart | 5m | 32,000years |

EOF 