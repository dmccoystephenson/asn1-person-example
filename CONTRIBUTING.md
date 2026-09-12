# Contributing

## Thank You

Thank you for your interest in contributing to ASN.1 Person Example! This guide will help you get started.

## Links

- [Repository](https://github.com/dmccoystephenson/asn1-person-example)

## Requirements

- A GitHub account
- Git installed on your local machine
- A C compiler (e.g. `gcc`)
- `make` installed
- `asn1c` installed ([installation instructions](https://github.com/Trihydro/asn1_codec/tree/develop/asn1c_combined#installing-asn1c))
- A basic understanding of C and ASN.1

## Getting Started

1. [Sign up for GitHub](https://github.com/signup) if you don't have an account.
2. Fork the repository by clicking **Fork** at the top right of the repo page.
3. Clone your fork: `git clone https://github.com/<your-username>/asn1-person-example.git`
4. Open the project in your editor.
5. Generate C sources and build: `asn1c -fcompound-names -fincludes-quoted -pdu=all person.asn && make -f converter-example.mk`
   If you encounter errors, please open an issue.

## Identifying What to Work On

### Issues

Work items are tracked as [GitHub issues](https://github.com/dmccoystephenson/asn1-person-example/issues).

### Milestones

Issues are grouped into [milestones](https://github.com/dmccoystephenson/asn1-person-example/milestones) representing upcoming releases.

## Making Changes

1. Make sure an issue exists for the work. If not, create one.
2. Switch to `main` and update it: `git checkout main && git pull`
3. Create a branch: `git checkout -b <branch-name>`
4. Make your changes.
5. Test your changes (see [Testing](#testing)).
6. Commit: `git commit -m "Description of changes"`
7. Push: `git push origin <branch-name>`
8. Open a pull request against `main`, link the related issue with `#<number>`.
9. Address review feedback.

## Testing

Verify your changes by running the encode/decode round-trip:

```bash
asn1c -fcompound-names -fincludes-quoted -pdu=all person.asn
make -f converter-example.mk
./converter-example -p Person -ixer -ouper person.xml > person.uper
./converter-example -p Person -iuper -oxer person.uper > decoded.xml
```

The contents of `decoded.xml` should match the original `person.xml`.

## Questions

Open a GitHub Discussion or issue in this repository.
