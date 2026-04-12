# Configuration Guide

This project does not use a runtime configuration file. All behaviour is controlled through the ASN.1 schema and command-line flags passed to `converter-example`.

## ASN.1 Schema (`person.asn`)

The schema defines the structure of the `Person` type that the converter operates on.

### name

**Type:** UTF8String
**Constraints:** None
**Description:** The name of the person, encoded as a UTF-8 string.

### age

**Type:** INTEGER
**Constraints:** 0–150
**Description:** The age of the person. Values outside the 0–150 range will be rejected during encoding.

## asn1c Compiler Flags

The following flags are used when generating C source files from the schema:

### -fcompound-names

**Default:** Off
**Description:** Generate longer, less ambiguous C identifiers to avoid naming collisions in complex schemas.

### -fincludes-quoted

**Default:** Off
**Description:** Use `#include "file.h"` instead of `#include <file.h>` in generated code.

### -pdu=all

**Default:** Off
**Description:** Generate encoder/decoder entry points for all top-level types defined in the schema.
