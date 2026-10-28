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
