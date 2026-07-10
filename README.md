# Ubuntu Pro documentation

This repository contains the source for the [Ubuntu Pro documentation](https://documentation.ubuntu.com/pro/).

Ubuntu Pro is a comprehensive subscription for open-source software security and
management running on Ubuntu LTS. This documentation covers setting up and
managing an Ubuntu Pro subscription, understanding the available services, and
getting support.

The documentation is built with the
[Sphinx Stack](https://documentation.ubuntu.com/sphinx-stack/) using the
[`canonical-sphinx`](https://github.com/canonical/canonical-sphinx) extension.

## Repository layout

- `docs/` – documentation source files and configuration
  - `docs/conf.py` – project-specific Sphinx configuration
  - `docs/requirements.txt` – Python build dependencies
  - `docs/Makefile` – build and check targets
  - `docs/_dev/` – tooling configuration (spelling, accessibility, linting)
  - `docs/_templates/` – custom HTML templates (Ubuntu Pro header)
  - `docs/reuse/links.txt` – reusable link definitions
- `.readthedocs.yaml` – Read the Docs build configuration
- `.github/workflows/` – documentation CI checks

## Building the documentation

All commands are run from the `docs/` directory.

Install the build environment and build the HTML output:

```bash
make -C docs install
make -C docs html
```

Build and serve the documentation locally with live reload:

```bash
make -C docs run
```

The documentation is then available at http://127.0.0.1:8000.

## Running the checks

```bash
make -C docs spelling     # spelling check
make -C docs linkcheck    # check for broken links
make -C docs woke         # inclusive language check
make -C docs vale         # style guide compliance
make -C docs pa11y        # accessibility check
```

To build the PDF output:

```bash
make -C docs pdf
```

## Contributing

Contributions are welcome. Please open an issue or pull request against this
repository. By contributing, you agree to the Canonical
[contributor licence agreement](https://ubuntu.com/legal/contributors) and the
Ubuntu [code of conduct](https://ubuntu.com/community/ethos/code-of-conduct).
