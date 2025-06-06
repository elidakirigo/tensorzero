# Developer Notes

> [!IMPORTANT]
>
> These notes are for developers who are working on the Python client itself, not for developers using the client for their own projects.

## Local Installation

To install the local version of the client (i.e. not from PyPI), run:

```bash
pip install -r requirements.txt
maturin develop
```

If using `uv`, then instead run:

```bash
uv venv
uv sync
uv run maturin develop --uv
uv run python
```

## Running tests

Integration tests can be run with `./test.sh` (this requires the same setup as `cargo test-e2e` - see `CONTRIBUTING.md`)

## Naming

There are several different names in use in this client:

- `python` - this is the name of the top-level directory for the Python client implementation.
- `tensorzero-python` - this is the rust _crate_ name, so that we get sensible output from running Cargo
- `tensorzero` - this is the name of the Python package (python code can use `import tensorzero`)
- `tensorzero_rust` - this is the (locally-renamed) Rust client package, which avoids conflicts with pyo3-generated code.
