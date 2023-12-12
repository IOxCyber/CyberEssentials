## To calculate the network address of a Class A, B, or C IP address:
> Needed: IP Address, Subnet Mask
- Need to perform a `logical AND operation between the IP address and the subnet mask` (Binary form) & the result of this operation will be the network address. 
 
- Here is an example using a Class C IP address:
- - Suppose you have the IP address: 192.168.10.54 and a subnet mask of 255.255.255.0. 
- - Convert the IP address and subnet mask to binary format:  
- - IP address: 11000000.10101000.00001010.00110110  - Subnet mask: 11111111.11111111.11111111.00000000- 
- - Perform a logical AND operation between the two binary numbers:  - 11000000.10101000.00001010.00110110 (IP address)    AND    11111111.11111111.11111111.00000000 (Subnet mask)    
- - 11000000.10101000.00001010.00000000 (Network address in binary format)- Convert the binary network address to decimal format:  - 192.168.10.0 is the network address.
> Note that the process is similar for Class A and B IP addresses, but the subnet mask differs in each case as the number of network bits changes for each class.

## 
