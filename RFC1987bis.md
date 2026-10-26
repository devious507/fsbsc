# RFC 1987bis: Rickroll over IPv6 (RoIPv6)

**Category:** Standards Track (Emotionally Damaging)  
**Status:** Humor / Questionable.  
**Intended Audience:** Anyone with a sense of humor  

## Abstract
This document specifies a mechanism for the unexpected delivery of Rick Astley audiovisual content over IPv6 networks. Particular attention is given to the use of IPv6-only services as a means of inducing otherwise rational network administrators to undertake disproportionate infrastructure modifications in pursuit of ostensibly enhanced content.

The protocol exploits a previously undocumented characteristic of network engineers: the inability to leave a technically interesting connectivity problem unsolved, regardless of the practical value of the destination.

## 1. Introduction
The Internet has historically relied upon social engineering to deliver unsolicited Rick Astley content. Existing implementations typically employ misleading hyperlinks, URL shorteners, or deceptive video thumbnails.

These mechanisms are insufficiently elaborate.
RoIPv6 introduces a mandatory infrastructure dependency, requiring the recipient to establish IPv6 connectivity before the payload can be delivered.

## 2. Protocol Requirements
An implementation conforming to this specification:
- MUST advertise exclusive IPv6 content.
- SHOULD encourage tunnel broker registration.
- MAY require WireGuard configuration.
- MUST NOT reveal the payload before successful IPv6 connectivity.
- MUST provide an experience indistinguishable from its IPv4 counterpart until the recipient has invested significant effort.
- SHOULD log the number of routers rebooted during negotiation.

## 3. Security Considerations
There are no known security considerations.
There are, however, considerable dignity considerations.

## 4. IANA Considerations
IANA is requested to reserve TCP port 1987 for RoIPv6.
Requests to reserve this port MUST be accompanied by a written apology.

##5. Experimental Validation
The feasibility of RoIPv6 has been demonstrated through an uncontrolled field experiment involving a technically competent network administrator.

The subject voluntarily established an IPv6 tunnel through Kansas City to access supposedly enhanced ASCII entertainment.

The attack required no credentials, no malware, and no exploitation of software vulnerabilities.

The only prerequisites were curiosity, technical competence, and an unreasonable willingness to solve interesting problems.

The experiment was considered successful when the subject, upon discovering the deception, began drafting this RFC.

**Acknowledgements:** The author wishes to thank the operators of towel.blinkenlights.nl for demonstratin that the most effective social engineering attacks require no malicious intent whatsoever.

## 6. Reference Implementation
For those wishing to see what all the fuss was about:

```text
telnet towel.blinkenlights.nl
telnet -6 towel.blinkenlights.nl
```
