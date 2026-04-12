# ASN.1 Person Example

## Description

ASN.1 Person Example is a minimal ASN.1 module compiled with `asn1c` that demonstrates how to encode and decode a `Person` object between XML (XER) and Unaligned PER (UPER) using the generated `converter-example` utility. It provides a foundation for experimenting with more complex ASN.1 structures.

## Installation

### Prerequisites

- A C compiler (e.g. `gcc`)
- `make`
- `asn1c` – Install from the [forked repository](https://github.com/Trihydro/asn1_codec/tree/develop/asn1c_combined#installing-asn1c)

### Building

1. Clone the repository: `git clone --recurse-submodules https://github.com/dmccoystephenson/asn1-person-example.git`
2. Generate C sources: `asn1c -fcompound-names -fincludes-quoted -pdu=all person.asn`
3. Build the converter: `make -f converter-example.mk`
4. Verify the build: `./converter-example -help`

## Usage

### Documentation

- [User Guide](USER_GUIDE.md) – Getting started and common scenarios
- [Commands Reference](COMMANDS.md) – Complete list of all CLI options
- [Configuration Guide](CONFIG.md) – ASN.1 schema options and compiler flags
- [Changelog](CHANGELOG.md) – Release-by-release summary of changes

### Quick Start

Encode XML to UPER:

    ./converter-example -p Person -ixer -ouper person.xml > person.uper

Decode UPER back to XML:

    ./converter-example -p Person -iuper -oxer person.uper > decoded.xml

## Support

### Experiencing a bug?

Please fill out a bug report [here](https://github.com/dmccoystephenson/asn1-person-example/issues/new).

- [Known Bugs](https://github.com/dmccoystephenson/asn1-person-example/issues?q=is%3Aissue+is%3Aopen+label%3Abug)

## Contributing

- [CONTRIBUTING.md](CONTRIBUTING.md)

## Testing

### Encode/Decode Round-Trip

Linux / macOS:

    asn1c -fcompound-names -fincludes-quoted -pdu=all person.asn
    make -f converter-example.mk
    ./converter-example -p Person -ixer -ouper person.xml > person.uper
    ./converter-example -p Person -iuper -oxer person.uper > decoded.xml

If `decoded.xml` matches the original `person.xml`, the test has passed.

## Development

### Setup

1. Clone the repository with submodules: `git clone --recurse-submodules https://github.com/dmccoystephenson/asn1-person-example.git`
2. Install `asn1c` following the [installation instructions](https://github.com/Trihydro/asn1_codec/tree/develop/asn1c_combined#installing-asn1c).
3. Generate C sources: `asn1c -fcompound-names -fincludes-quoted -pdu=all person.asn`
4. Build: `make -f converter-example.mk`

### Inspecting Encoded Data

Since UPER output is binary, you can inspect it with `xxd`:

    xxd -b person.uper   # show bits
    xxd person.uper      # show hex

## Authors and Acknowledgement

### Developers

| Name | Main Contributions |
|------|--------------------|
| [dmccoystephenson](https://github.com/dmccoystephenson) | Initial project setup and documentation |

## Project Status

This project is in active development.
