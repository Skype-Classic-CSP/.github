Skype uses the SuperNode mechanism and a peer-to-peer network, as well as UDP and TCP protocols. First, let’s look at UDP.

During authorization, Skype sends a probe packet to UDP servers to check the availability of SuperNode.

He doesn’t wait for a response from the server; if it didn’t respond, then it didn’t respond — he just keeps going.
There are three types of packetType:

| packetType | Byte | Direction| Description |
|---|---|---|---|
| PKT_TYPE_OBFSUK | 0x02 | C >> S, S >> C | used for an encrypted RC4 packet with the header described above |
| PKT_TYPE_RESEND | 0x03 | C >> S | the packet was sent again, with a different header |
| PKT_TYPE_NACK | 0x07 | S >> C | request to resend the packet; it contains the client's IP address |

<a href="#">The structure of the PKT_TYPE_RESEND packet</a>
<a href="#">The structure of the PKT_TYPE_NACK packet</a>
