Skype uses the SuperNode mechanism and a peer-to-peer network, as well as UDP and TCP protocols. First, let’s look at UDP.

During authorization, Skype sends a probe packet to UDP servers to check the availability of SuperNode.


He doesn’t wait for a response from the server; if it didn’t respond, then it didn’t respond — he just keeps going.

Structure of the probe packet:

Header:
| Field | Byte | len | Description |
|---|---|---|---|
| transId | `02 01` | 2 bytes | The serial number of the packet |
| packetType | `02` | 1 byte| Packet Type |
| unknown field | `N/A` | 9 bytes | ??? |
| Crc32 | `N/A` | 4 bytes | CRC32 of the encrypted payload |
