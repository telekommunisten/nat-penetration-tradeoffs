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

.. _`ambient authority`: http://www.erights.org/talks/no-sep/


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



conclusion
``````````

The first obstacle software developers encounter when building decentralized systems is this NAT problem;
to solve this problem with NAT-PMP or UPnP is to depend on the quality of the NAT device being utilized. Furthermore
if Alice and Bob are both behind partial-cone NAT devices then utilizing ICE implies failing back to a TURN proxy server;
the single point of failure. For many applications the higher latency of onion services can be tolerated in exchange
for a more reliable solution.


Tor design documents
````````````````````

- `Tor Prop 224`_ - Next-Generation Hidden Services in Tor 
- `Tor Prop 250`_ - Random Number Generation During Tor Voting


.. _`Tor Prop 224`: https://gitweb.torproject.org/torspec.git/tree/proposals/224-rend-spec-ng.txt
.. _`Tor Prop 250`: https://gitweb.torproject.org/torspec.git/tree/proposals/250-commit-reveal-consensus.txt


RFC references
``````````````

.. [RFC5245] Interactive Connectivity Establishment (ICE) https://tools.ietf.org/html/rfc5245
.. [RFC5389] Session Traversal Utilities for NAT (STUN) https://tools.ietf.org/html/rfc5389
.. [RFC5766] Traversal Using Relays around NAT (TURN) https://tools.ietf.org/html/rfc5766
.. [RFC6886] NAT Port Mapping Protocol (NAT-PMP) https://tools.ietf.org/html/rfc6886
.. [RFC6887] Port Control Protocol (PCP) https://tools.ietf.org/html/rfc6887
.. [RFC6970] Universal Plug and Play (UPnP) https://tools.ietf.org/html/rfc6970
