Skype uses the SuperNode mechanism and a peer-to-peer network, as well as UDP and TCP protocols. First, let’s look at UDP.

During authorization, Skype sends a probe packet to UDP servers to check the availability of SuperNode.


He doesn’t wait for a response from the server; if it didn’t respond, then it didn’t respond — he just keeps going.

Structure of the probe packet:

Header:
| Field | Byte | len | Order | Description |
|---|---|---|---|---|
| transId | `N/A` | 2 bytes | BE | The serial number of the packet |
| packetType | `N/A` | 1 byte| - | Packet Type |
| IV | `N/A` | 4 bytes | BE | IV for RC4 Key |
| CRC32 | `N/A` | 4 bytes | BE | CRC32 of the encrypted payload |

There are three types of packetType:

| packetType | Byte | Direction| Description |
|---|---|---|---|
| PKT_TYPE_OBFSUK | 0x02 | C >> S, S >> C | used for an encrypted RC4 packet with the header described above |
| PKT_TYPE_RESEND | 0x03 | C >> S | the packet was sent again, with a different header |
| PKT_TYPE_NACK | 0x07 | S >> C | request to resend the packet |
