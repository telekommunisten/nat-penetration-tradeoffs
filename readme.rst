
=================================
 NAT penetration tradeoffs chart
=================================


motivation
``````````

Network Address Translation violates the end to end principal, making it much more difficult
to build decentralized systems on the Internet.


NAT penetration tradeoffs chart
```````````````````````````````

+----------------------------------------+------------------------------------------------------------------------------------+
| Design Property                        | Proposed NAT penetration solution                                                  |
+========================================+===================+======================+==================+===============+======+
| **advantages**                         | Tor Onion Service | Direct Onion Service | ICE w/ STUN+TURN | NAT-PMP / PCP | UPnP |
+----------------------------------------+-------------------+----------------------+------------------+---------------+------+
| low latency                            |                   |                      |\+                |\+             |\+    |
+----------------------------------------+-------------------+----------------------+------------------+---------------+------+
| preserves anonymity of the client      |\+                 |\+                    |                  |               |      |
+----------------------------------------+-------------------+----------------------+------------------+---------------+------+
| preserves anonymity of the server      |\+                 |                      |                  |               |      |
+----------------------------------------+-------------------+----------------------+------------------+---------------+------+
| uses a decentralized rendezvous        |\+                 |\+                    |                  |               |      |
+----------------------------------------+-------------------+----------------------+------------------+---------------+------+
| **disadvantages**                      | Tor Onion Service | Direct Onion Service | ICE w/ STUN+TURN | NAT-PMP / PCP | UPnP |
+----------------------------------------+-------------------+----------------------+------------------+---------------+------+
| not yet implemented                    |                   |\+                    |                  |               |      |
+----------------------------------------+-------------------+----------------------+------------------+---------------+------+
| uses a centralized rendezvous          |                   |                      |\+                |               |      |
+----------------------------------------+-------------------+----------------------+------------------+---------------+------+
| varying implementation quality         |                   |                      |                  |\+             |\+    |
+----------------------------------------+-------------------+----------------------+------------------+---------------+------+


evaluation of designs
`````````````````````


References
----------

.. [RFC5245] Interactive Connectivity Establishment (ICE)
.. [RFC5389] Session Traversal Utilities for NAT (STUN)
.. [RFC5766] Traversal Using Relays around NAT (TURN)
.. [RFC6886] NAT Port Mapping Protocol (NAT-PMP)
.. [RFC6887] Port Control Protocol (PCP)
