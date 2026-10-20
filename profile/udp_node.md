Skype uses the SuperNode mechanism and a peer-to-peer network, as well as UDP and TCP protocols. First, let’s look at UDP.

During authorization, Skype sends a probe packet to UDP servers to check the availability of SuperNode.


He doesn’t wait for a response from the server; if it didn’t respond, then it didn’t respond — he just keeps going.

Structure of the probe packet:

Header:
| Field | Byte | Description |
|---|---|---|
| transId | `02 01` | The serial number of the packet |
| packetType | `02` | Packet Type |
| unknown field | `N/A` | ??? |
| Crc32 | `N/A` | CRC32 of the encrypted payload |
