=================================
 NAT penetration tradeoffs chart
=================================


motivation
``````````

Network Address Translation violates the end to end principal, making it much more difficult
to build decentralized systems on the Internet. It is our hope that software developers will become
more aware of the technical, political, economic and cultural implications of the proposed solutions
to this violation of the end to end principal.

Despite the Edward Snowden apocalypse, many technologists are stuck in the post-surveillance mindset and
don't give much thought to providing anonymity guarantees. When a software developer releases communication
software, there should be more thought with regards to social responsibility; Does my software allow
rich corporations to become richer? Does my software system create excess or `ambient authority`_?



NAT penetration tradeoffs chart
```````````````````````````````

+----------------------------------------+------------------------------------------------------------------------------------------+
| Design Property                        | Proposed NAT penetration solution                                                        |
+========================================+===================+======================+=====+==================+===============+======+
| **advantages**                         | Tor Onion Service | Direct Onion Service | i2p | ICE w/ STUN+TURN | NAT-PMP / PCP | UPnP |
+----------------------------------------+-------------------+----------------------+-----+------------------+---------------+------+
| low latency                            |                   |                      |     |\+                |\+             |\+    |
+----------------------------------------+-------------------+----------------------+-----+------------------+---------------+------+
| works on all NAT topologies            |\+                 |\+                    |\+   |\+                |               |      |
+----------------------------------------+-------------------+----------------------+-----+------------------+---------------+------+
| preserves anonymity of the client      |\+                 |\+                    |\+   |                  |               |      |
+----------------------------------------+-------------------+----------------------+-----+------------------+---------------+------+
| preserves anonymity of the server      |\+                 |                      |\+   |                  |               |      |
+----------------------------------------+-------------------+----------------------+-----+------------------+---------------+------+
| uses a decentralized rendezvous        |\+                 |\+                    |     |                  |               |      |
+----------------------------------------+-------------------+----------------------+-----+------------------+---------------+------+
| **disadvantages**                      | Tor Onion Service | Direct Onion Service | i2p | ICE w/ STUN+TURN | NAT-PMP / PCP | UPnP |
+----------------------------------------+-------------------+----------------------+-----+------------------+---------------+------+
| not yet implemented                    |                   |\-                    |     |                  |               |      |
+----------------------------------------+-------------------+----------------------+-----+------------------+---------------+------+
| compatible with TCP only               |\-                 |\-                    |     |                  |               |      |
+----------------------------------------+-------------------+----------------------+-----+------------------+---------------+------+
| requires support by the NAT itself     |                   |                      |     |                  |\-             |\-    |
+----------------------------------------+-------------------+----------------------+-----+------------------+---------------+------+
| uses a centralized rendezvous          |                   |                      |     |\-                |               |      |
+----------------------------------------+-------------------+----------------------+-----+------------------+---------------+------+
| varying implementation quality         |                   |                      |     |                  |\-             |\-\-\-|
+----------------------------------------+-------------------+----------------------+-----+------------------+---------------+------+



evaluation of designs
`````````````````````


References
----------

.. [RFC5245] Interactive Connectivity Establishment (ICE)
.. [RFC5389] Session Traversal Utilities for NAT (STUN)
.. [RFC5766] Traversal Using Relays around NAT (TURN)
.. [RFC6886] NAT Port Mapping Protocol (NAT-PMP)
.. [RFC6887] Port Control Protocol (PCP)
.. [RFC6970] Universal Plug and Play (UPnP)






.. _`ambient authority`: http://www.erights.org/talks/no-sep/
