---
docname: draft-ietf-avtcore-rtp-payload-registry-latest
title: Closing the IANA RTP Payload Format Registry 
abbrev: Close RTP Payload Registry
updates: 4855, 8088 
cat: std
ipr: trust200902
wg: AVTCORE
area: ART
submissiontype: IETF  # also: "independent", "IAB", or "IRTF"

venue:
  group: AVTCORE
  mail: avt@ietf.org
  github: gloinul/draft-ietf-avtcore-rtp-payload-registry

author:
-
   ins:  M. Westerlund
   name: Magnus Westerlund
   org: Ericsson
   email: magnus.westerlund@ericsson.com

informative:


normative:
  RFC2119:
  RFC4855:
  RFC8088:
  
--- abstract


--- middle

# Introduction {#introduction}



# Conventions

{::boilerplate bcp14}


# IANA Considerations {#IANA-Consideration}


| Cause Code | Meaning | Reference | Contact |
| 0 | Error in the Protection Engine List | RFC-To-Be | Authors |
| 1 | Error During Protection Handshake | RFC-To-Be | Authors|
| 2 | Failure in Protection Engines Validation | RFC-To-Be | Authors |
| 3 | Timeout During KEY Handshake or Validation | RFC-To-Be | Authors |
| 4-65534 | Available for Assignment | RFC-To-Be | Authors |
| 65535 | Reserved | RFC-To-Be | Authors |
{: #iana-protection-error-cause title="Protection Error Cause Code" cols="r l l l"}


# Security Considerations {#Security-Considerations}

xs

# Acknowledgments

   The authors thank Michael Tüxen for his invaluable comments
   helping to cope with Association Restart, ASCONF handling and
   restructuring the Protection Engine architecture.
