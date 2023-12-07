## Protocols
`TCP/IP (Transmission Control Protocol)`:
```
+
Connection-oriented, build connection before transmitting data.
Reliable; guarantees delivery by retransmission of data, Checks for errors in data packets
Sequenced, packets arrive in-order at the receiving device.
-
Slower than UDP due to error checking, building connection, gurantees delivery.
Unable to execute broadcasting tasks.

Uses: Email, World Wide Web (HTTP, HTTPS)
```

`UCP (User Datagram Protocol)`:
```
+
Faster,Simple in its transmission, limited data management.
Supports broadcasting tasks.

-
Unreliable, cannot guarantee packet delivery due to being datagram-oriented rather than connection-oriented.
No retransmission, Minimal error checking.
No sequencing, packets may arrive out of order.
Can overload the receiver, only stops sending data once the task is completed.

Uses: Video Streaming, Online Gaming
```
