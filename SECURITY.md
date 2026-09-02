# Security policy

## Important: this repository contains deliberately PII-shaped test data

Before you report anything, please read this section.

`seeds/loan.csv` contains columns named `social_security_number`, `ssn`,
`ssnumber`, `ssnumber1`, `drivers_license`, `dl`, `zip_code`, `emp_title` and
`c_url`. **These are synthetic.** The values are sequential placeholders
(`100000000`, `100000001`, …, `DL500000`, `DL500001`, …) and correspond to no
real person.

They exist on purpose. Learning to find and exclude redundant identity columns
before an AI agent sees them is the governance exercise this track is built
around — see "The governance beat" in the [README](README.md).

Likewise, `seeds/fpr_records.csv` contains name and email columns. The names are
`Persona Customer N` and the addresses are `@example.com`, a domain reserved by
RFC 2606 precisely for this purpose.

Automated PII and secret scanners will flag these files. That is expected.

## Reporting a vulnerability

Please do not open a public GitHub issue for security problems.

If you believe you have found a security vulnerability in this repository,
report it privately to **security@dbtlabs.com**. Include:

- A description of the issue and why you believe it is a security problem
- Steps to reproduce, if applicable
- The commit SHA or file path where you found it
- Any suggested remediation

You will receive an acknowledgement of your report. Because this repository is
workshop material rather than a supported product, response and remediation are
best effort — see the support expectations in the [README](README.md).

**Do report** anything that looks like real data. If you find values in this
repository that appear to belong to an actual person or organization — rather
than the synthetic placeholders described above — treat that as a vulnerability
and use the process above. The same goes for committed credentials or key
material.

## Out of scope

- The PII-shaped columns in `seeds/loan.csv` described above.
- Deliberate data-quality problems in the seed files: empty strings in numeric
  columns, percentages stored as text, `NA` sentinel values. These are part of
  the exercise, not defects.
- Vulnerabilities in third-party dbt packages listed in `packages.yml`. Report
  those to the relevant package maintainer.
