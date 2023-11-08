---
docname: draft-ietf-avtcore-rtp-payload-registry-latest
title: Closing the IANA RTP Payload Format Media Type Registry
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

  IANA-REG:
    target: "https://datatracker.ietf.org/doc/draft-westerlund-tsvwg-sctp-crypto-dtls/"
    title: "IANA's registry for RTP Payload Format Media Types"
    date: Nov 2023


--- abstract

This document closes the IANA Registry for RTP Payload formats Media Types.

--- middle

# Introduction {#introduction}



# Conventions

{::boilerplate bcp14}


# IANA Considerations {#IANA-Consideration}

IANA is requested to add the following missing RTP Payload types to
the "RTP Payload Format Media Types" registry {{IANA-REG}}.

| Media Type | Sub Type | Clock Rate (Hz) | Channels (audio) | Reference Reference |
| video | VP8 | 90000 | | RFC7741 |
| video | AV1 | 90000 | | https://www.iana.org/assignments/media-types/video/AV1 |
| video | HEVC | 90000 | | RFC7798 |
| video | VVC | 90000 | | RFC9328 |
{: #iana-entries title="Payload Types to Register in RTP Payload Format Media Types" cols="l l l l l"}

IANA is further requested to close the "RTP Payload Format Media
Types" registry {{IANA-REG}}. IANA should add the following to the note to the registry:

"This registry


# Security Considerations {#Security-Considerations}

This document has no security considerations as it defines an adminstrative rule change.

--- back

# Acknowledgments

   The author likes to thank ...
