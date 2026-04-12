# Copilot Instructions

This repository follows the DPC (Dans Plugins Community) conventions defined at
https://github.com/Dans-Plugins/dpc-conventions. Read those conventions before
making any changes.

## Technology Stack

- Language: C (generated from ASN.1 via `asn1c`)
- Build tool: make
- ASN.1 compiler: asn1c
- Test approach: encode/decode round-trip verification

## Project Structure

- `person.asn` – ASN.1 schema defining the `Person` type
- `person.xml` – Sample XML input for testing
- `usdot-asn1c/` – Git submodule providing the `asn1c` compiler
- `.github/workflows/` – CI and release automation

## Coding Conventions

- Keep the ASN.1 schema minimal and well-commented.
- Use `asn1c` flags `-fcompound-names -fincludes-quoted -pdu=all` when generating code.
- Do not commit generated C source files; they are produced at build time.

## Contribution Workflow

- Branch from `develop` for all changes.
- Open a pull request against `develop`, not `main`.
- Reference the related GitHub issue in every pull request description.
