Skype uses the SuperNode mechanism and a peer-to-peer network, as well as UDP and TCP protocols. First, let’s look at UDP. 
During authorization, Skype sends a probe packet to UDP servers to check the availability of SuperNode.

He doesn’t wait for a response from the server; if it didn’t respond, then it didn’t respond — he just keeps going.

| Packet Type | Description | Server Behavior |
|---|---|---|
| `PKT_TYPE_OBFSUK` | Obfuscated UDP packet | Sends a NACK response |
| `PKT_TYPE_RESEND` | Probe/request packet | Decrypts the payload and validates CRC32 |
| Unknown | Unsupported packet type | Sends a NACK response |
