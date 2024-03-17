---
docname: draft-westerlund-avtcore-rtp-payload-registry-latest
title: Closing the RTP Payload Format Media Types IANA Registry
abbrev: Close RTP Payload Formats Registry
updates: 8088
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
  RFC8088:

  RTP-FORMATS:
    target: "https://www.iana.org/assignments/rtp-parameters/rtp-parameters.xhtml#rtp-parameters-2"
    title: "IANA's registry for RTP Payload Format Media Types"
    date: Nov 2023

  MEDIA-TYPES:
    target: "https://www.iana.org/assignments/media-types/media-types.xhtml"
    title: "IANA's registry for Media Types"
    date: Nov 2023


--- abstract

It has been observed that specifications of new RTP Paylaod formats
forgets to register in the IANA regsitry "RTP Payload formats Media
Types". In practice this have no real impact. One reason is that the
Media Types registry is the crucial regsistry to register any Media
Type to establish the media type used to identified the format in
various signalling usage.

To resolve this sitaution this document performs the following. First
it updates the registry to include known RTP Payload formats at the
time of writing. Then closes the IANA Registry for RTP Payload formats
Media Types for future registration. Beyond instructing IANA to close
this registry the instruction to authors in RFC 8088 are updated that
registration is no longer required in the closed registry.

--- middle

# Introduction {#introduction}

It has been observed that specifications of new RTP Paylaod formats
forgets to register in the IANA regsitry "RTP Payload formats Media
Types" {{RTP-FORMATS}}. In practice this have no real impact. This
registry are not used for any purposes other than to track which media
types actually have RTP payload formats. That purpose could be
addressed through other means.

It is the Media Types registry {{MEDIA-TYPES}} is the crucial
regsistry to register any Media Type to establish the media type used
to identified the format in various signalling usage and avoid
collisions and for reference of their specification.

To resolve this sitaution this document performs the following. First
it updates the registry to include known RTP Payload formats at the
time of writing. Then closes the IANA Registry for RTP Payload formats
Media Types for future registration. Beyond instructing IANA to close
this registry the instruction to authors in {{RFC8088}} are updated that
registration in the closed registry is no longer required.

# Conventions

{::boilerplate bcp14}


# Update to How To Write an RTP Payload Format

How to write an RTP Payload format {{RFC8088}} mandates that RTP
Payload formats shall register in RTP Payload Format media types:

"Since all RTP payload formats contain a media type specification,
they also need an IANA Considerations section.  The media type name
must be registered, and this is done by requesting that IANA register
that media name.  When that registration request is written, it shall
also be requested that the media type is included under the "RTP
Payload Format media types" subregistry of the RTP registry
(http://www.iana.org/assignments/rtp-parameters)."

This paragraph is changed to the following:

"Since all RTP payload formats contain a media type specification,
they also need an IANA Considerations section.  The media type name
must be registered, and this is done by requesting that IANA register
that media name."

Thus removing the need to register in the "RTP
Payload Format media types".

# IANA Considerations {#IANA-Consideration}

IANA is requested to add the following missing RTP Payload types to
the "RTP Payload Format Media Types" registry {{RTP-FORMATS}}.

| Media Type | Sub Type | Clock Rate (Hz) | Channels (audio) | Reference Reference |
| video | VP8 | 90000 | | RFC7741 |
| video | AV1 | 90000 | | https://www.iana.org/assignments/media-types/video/AV1 |
| video | HEVC | 90000 | | RFC7798 |
| video | VVC | 90000 | | RFC9328 |
{: #iana-entries title="Payload Types to Register in RTP Payload Format Media Types" cols="l l l l l"}

IANA is further requested to close the "RTP Payload Format Media
Types" registry {{RTP-FORMATS}} for any further registrations. IANA
should add the following to the note to the registry:

"This registry has been closed as it was considered redundant as all
RTP Payload formats are part of the Media Types registry
(https://www.iana.org/assignments/media-types/media-types.xhtml). For
further motivation see (RFC-TBD1)."

RFC-Editor Note: Please replace RFC-TBD1 with the RFC number of this
specification and then remove this note.

# Security Considerations {#Security-Considerations}

This document has no security considerations as it defines an adminstrative rule change.

--- back

# Acknowledgments

   The author likes to thank ...
