
Eventually this will be a Crossy Roads client.

Discovery
---------

Crossy Roads announces itself via mDNS as

  crossy-roads._tcp

Protocol
--------

The protocol runs over TCP.

Each message is prefixed with 0x01, followed by a byte giving the type
of message.  Almost always what follows is some fixed number of signed
little-endian 32-bit integers.

Client messages
------------------

Play again:

  0168 01000000 02

The final byte in this message is the exception to the rule of 32-bit
ints in the protocol.

Move:

  0164 dir player 00000000


directions:

  1 -> forward
  2
  3
  4 -> right
  -1
  -2
  -3
  -4

Server messages
---------------

  0165
  0166
  0167
