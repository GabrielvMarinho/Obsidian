Every [[API]] is technically a protocol, but not every protocol is at network level.

TCP is a transport level protocol.
HTTP built on top of tcp, and is an application level protocol.
Your application is also a protocol, build on top of HTTP, creating a "new layer"



## Difference of each level

Generally, application protocols are very easy to setup, but network protocols are often tightly integrated with the OS kernel or network hardware

| Aspect              | Network Layer Protocols                                                      | application Layer Protocols                         |
| ------------------- | ---------------------------------------------------------------------------- | --------------------------------------------------- |
| OSI Model Layer     | It works on Layer 3.                                                         | In works on Layer 7.                                |
| Purpose             | Facilitate communication between devices                                     | Facilitate communication between applications/users |
| scope               | Entire network                                                               | Specific application                                |
| Network Addresses   | Uses IP addresses                                                            | No standard addressing scheme                       |
| routing             | Determines the path packets take through network                             | Not involved in routing                             |
| Transport Protocols | Uses protocols like TCP and UDP                                              | Can use protocols like HTTP, FTP, SMTP, etc.        |
| Reliability         | Less reliable due to potential packet loss                                   | More reliable due to built-in error checking        |
| Error Handling      | Typically relies on upper layer protocols for error detection and correction | Built-in error detection and correction mechanisms  |
| Packet Size         | Supports larger packet sizes                                                 | Smaller packet sizes                                |
| Network Topology    | Can handle complex network topologies                                        | Limited to simpler network topologies               |
