---
docname: draft-ietf-avtcore-rtp-payload-registry-latest
title: Closing the RTP Payload Format Media Types IANA Registry
abbrev: Close RTP Payload Formats Registry
updates: 8088
cat: std
ipr: trust200902
wg: AVTCORE
area: WIT
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
  RFC4855:


normative:
  RFC2119:
  RFC8088:

  RTP-FORMATS:
    target: "https://www.iana.org/assignments/rtp-parameters/rtp-parameters.xhtml#rtp-parameters-2"
    title: "IANA's registry for RTP Payload Format Media Types"
    date: Nov 2023

  MEDIA-TYPES:
    target: "https://www.iana.org/assignments/media-types/media-types.xhtml"
    title: "IANA's registry for Media Types"
    date: Nov 2023

  AV1-Media-Type:
    target: "https://www.iana.org/assignments/media-types/video/AV1"
    title: "IANA Media Type Entry for video/AV1"
    date: Jan 2021

--- abstract

A number of authors of RTP Payload Formats and the WG process have
failed to ensure that the media types for RTP payload formats is
registred in the IANA registry "RTP Payload Formats Media Types" as
recommended by RFC 8088. To simplify the process and rely only on the
media types registry this document closes the RTP payload specific
registry. In addition it updates the instruction to payload format
authors in RFC 8088 to reflect this change.


--- middle

# Introduction {#introduction}

It has been observed that specifications of new Real-time Transport Protocol
(RTP) payload formats often forget to specify registration of the format's media
type in the IANA registry "RTP Payload Formats Media Types" {{RTP-FORMATS}} as
recommended by {{RFC8088}}.  In practice this has no real impact. This registry
is not used for any purpose other than to track which media types actually have
RTP payload formats. That purpose could be addressed through other means.

The Media Types registry {{MEDIA-TYPES}} is the crucial
registry to register any Media Type to establish the media type used
to identify the format in various signalling usages, to avoid
collisions, and to reference their specifications.

To resolve this situation, this document performs the following actions. First,
it updates the registry to include known RTP payload formats at the
time of writing. Then, it closes the IANA Registry for RTP Payload Formats
Media Types for future registration. Beyond instructing IANA to close
this registry, the instructions to authors in {{RFC8088}} are updated so that
registration in the closed registry is no longer mentioned.

The origins of the "RTP Payload Formats Media Types" registry, as referenced in
{{RTP-FORMATS}}, are unclear. The registry cites {{RFC4855}} as providing the
instructions for its maintenance. However, upon reviewing RFC 4855, no text has
been found that defines the registry's purpose and operational rules. Further
attempts to trace the registry's creation have failed to uncover any references
to its establishment. It is likely that the registry was created based on
correspondence via email or at the request of an Area Director (AD).
Consequently, there is no known existing specification for this registry that
requires updating upon its closure.


# Update to How To Write an RTP Payload Format

How to write an RTP Payload format {{RFC8088}} mandates in its section
on IANA Considerations (Section 7.4) that RTP Payload formats shall
register in RTP Payload Format media types. This paragraph is changed
without affecting its status as part of an informational RFC. Thus
removing the need to register in the "RTP Payload Format media types".


OLD:

"Since all RTP payload formats contain a media type specification,
they also need an IANA Considerations section.  The media type name
must be registered, and this is done by requesting that IANA register
that media name.  When that registration request is written, it shall
also be requested that the media type is included under the "RTP
Payload Format media types" sub-registry of the RTP registry
(http://www.iana.org/assignments/rtp-parameters)."

NEW:

"Since all RTP payload formats contain a media type specification,
they also need an IANA Considerations section.  The media type name
must be registered, and this is done by requesting that IANA register
that media name in the Media Types registry
(https://www.iana.org/assignments/media-types/media-types.xhtml)."


# IANA Considerations {#IANA-Consideration}

IANA is requested to add the following missing RTP Payload types to
the "RTP Payload Format Media Types" registry {{RTP-FORMATS}}.

| Media Type | Sub Type | Clock Rate (Hz) | Channels (audio) | Reference |
| application | flexfec | | | RFC8627 |
| audio | EVRCNW | 16000 |  | RFC6884 |
| audio | EVRCNW0 | 16000 |  | RFC6884 |
| audio | EVRCNW1 | 16000 |  | RFC6884 |
| audio | aptx |  |  | RFC7310 |
| audio | opus | 48000 |  | RFC7587 |
| audio | G711-0 | |  | RFC7650 |
| audio | flexfec | |  | RFC8627 |
| text | flexfec | | | RFC8627 |
| text | ttml+xml | | | RFC8759 |
| video | VP8 | 90000 | | RFC7741 |
| video | AV1 | 90000 | | {{AV1-Media-Type}} |
| video | HEVC | 90000 | | RFC7798 |
| video | smpte291 |  | | RFC8331 |
| video | VVC | 90000 | | RFC9328 |
| video | EVC | 90000 | | RFC9584 |
| video | flexfec |  | | RFC8627 |
{: #iana-entries title="Payload Types to Register in RTP Payload Format Media Types" cols="l l l l l"}

IANA is requested to update the following RTP Payload types in the "RTP Payload Format Media Types" registry {{RTP-FORMATS}}.

| Media Type | Sub Type | Clock Rate (Hz) | Channels (audio) | Reference |
| audio | MP4A-LATM |  | | RFC6416 |
| video | MP4V-ES | 90000 | | RFC6416 |
{: #iana-update-entries title="Payload Types to update in RTP Payload Format Media Types" cols="l l l l l"}


IANA is further requested to close the "RTP Payload Format Media
Types" registry {{RTP-FORMATS}} for any further registrations. IANA
should add the following to the existing note for the registry:

NEW:

"This registry has been closed as it was considered redundant as all
RTP Payload formats are part of the Media Types registry
(https://www.iana.org/assignments/media-types/media-types.xhtml). For
further motivation see (RFC-TBD1)."

In addition, it is requested that the existing note of "RTP Payload Format Media
Types" registry {{RTP-FORMATS}} is changed in the following way:

OLD:
Registration procedures and a registration template can be found in [RFC4855].

NEW:
It was previously stated that registration procedures and a registration
template can be found in [RFC4855].  This is not actually the case as
discussed by [RFC-TBD1].

RFC-Editor Note: Please replace RFC-TBD1 with the RFC number of this
specification and then remove this note.

# Security Considerations {#Security-Considerations}

This document has no security considerations as it defines an administrative rule change.

--- back

# Acknowledgments

 The author likes to thank Jonathan Lennox, Zaheduzzaman Sarker,
 Bernard Aboba, Elwyn Davies, Wes Hardaker, Gunter Van de Velde, Éric
 Vyncke, Mahesh Jethanandani, and Hyunsik Yang for review and editorial fixes.
