a [[Python]] package management it bundles a bunch of existing tools like pip, venv, etc, but make it faster, made in [[Rust]].


start a project:
```bash
uv init hello
```

run the project:
```bash
cd test
uv run main.py
```


adding this to the project.toml:
```toml
[build-system]
requires = ["setuptools>=42", "wheel"]
build-backend = "setuptools.build_meta"

[project.scripts]
shortcut = "main:main"
```

you can run the project with:
```bash
uv run shortcut
```
