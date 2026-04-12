# Commands Reference

This document lists the commands available through the `converter-example` utility built from the ASN.1-generated code.

## converter-example

The `converter-example` utility encodes and decodes ASN.1 data between different transfer syntaxes.

### Synopsis

```
./converter-example -p <PDU> -i<input-format> -o<output-format> [input-file]
```

### Options

#### -p \<PDU\>

**Description:** Specify the top-level ASN.1 type (Protocol Data Unit) to encode or decode.
**Required:** Yes
**Example:** `-p Person`

#### -ixer

**Description:** Set the input format to XER (XML Encoding Rules).
**Example:** `-ixer`

#### -iuper

**Description:** Set the input format to UPER (Unaligned Packed Encoding Rules).
**Example:** `-iuper`

#### -oxer

**Description:** Set the output format to XER (XML Encoding Rules).
**Example:** `-oxer`

#### -ouper

**Description:** Set the output format to UPER (Unaligned Packed Encoding Rules).
**Example:** `-ouper`

#### -help

**Description:** Display usage information and supported formats.
**Example:** `./converter-example -help`

## Examples

### Encode XML to UPER

```bash
./converter-example -p Person -ixer -ouper person.xml > person.uper
```

### Decode UPER to XML

```bash
./converter-example -p Person -iuper -oxer person.uper > decoded.xml
```
