These are security patches applied to versions of MaraDNS after
3.5.0036 (2023):

* [DNS-over-TCP patch](MaraDNS-sendtcp.patch.txt).  There was a denial of
  service where a trusted user authorized to perform queries could disable 
  DNS-over-TCP until Deadwood was restarted.  The hole only worked when
  DNS-over-TCP was enabled, a non-default configuration.  Date: 2026-06-11
  MaraDNS 3.5.0037 has this patch already applied.

* [DNS-over-TCP patch 2](MaraDNS-recvtcp.patch.txt).  Another denial of
  service bug in MaraDNS’s (actually Deadwood’s) DNS-over-TCP code.  The
  only impact was that DNS-over-TCP could be disabled by an attacker;
  DNS-over-UDP was not impacted.  Date: 2026-08-24

* [RFC 8482 patch](MaraDNS-rfc8482.patch.txt).  Deadwood, when generating
  a RFC8482 response, would make visible 19 bytes of unallocated memory on
  the heap to the network.  Dated: 2026-09-01
