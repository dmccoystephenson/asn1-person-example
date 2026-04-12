# User Guide

## Prerequisites

- A C compiler (e.g. `gcc`)
- `make`
- `asn1c` – Install from the [forked repository](https://github.com/Trihydro/asn1_codec/tree/develop/asn1c_combined#installing-asn1c)

## First Steps

After cloning the repository, generate the C source files from the ASN.1 schema and build the converter utility:

```bash
asn1c -fcompound-names -fincludes-quoted -pdu=all person.asn
make -f converter-example.mk
```

Verify the build by running:

```bash
./converter-example -help
```

You should see output listing the supported input/output formats (XER, UPER, etc.).

## Common Scenarios

### Encode XML to UPER

Convert an XML-encoded `Person` record to Unaligned PER (UPER) binary format:

```bash
./converter-example -p Person -ixer -ouper person.xml > person.uper
```

### Decode UPER to XML

Convert a UPER-encoded `Person` record back to XML:

```bash
./converter-example -p Person -iuper -oxer person.uper > decoded.xml
```

### Inspect Binary Data

Since UPER output is binary, use `xxd` to inspect it:

```bash
xxd -b person.uper   # show bits
xxd person.uper      # show hex
```

## Schema Overview

The `person.asn` file defines a single ASN.1 module:

| Field | Type | Constraints |
|-------|------|-------------|
| `name` | UTF8String | None |
| `age` | INTEGER | 0–150 |
