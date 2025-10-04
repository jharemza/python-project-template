# python-project-template

A **Copier-based**, **Docker-friendly**, and **batteries-included** starter template for new Python projects.

---

## Why this template exists

Creating a new Python project invariably involves copying boilerplate: virtual environments, tooling configs, CI pipelines, linting rules, directory structure, etc. This template captures all of that so you don’t have to reinvent it each time — you just fill in a few parameters and get a ready-to-go project.

---

## Key Features

- **Interactive scaffolding** via [Copier](https://copier.readthedocs.io/) — generates a project according to your answers (project name, slug, whether to include CI, etc.)
- **Consistent structure**:

    ```text
    src/
    tests/
    .pre-commit-config.yaml
    pyproject.toml
    README.md
    .github/workflows/ci.yml
    .gitignore
    ```

- **Template-based config files** — files like `pyproject.toml.jinja`, `ci.yml.jinja`, `.pre-commit-config.yaml.jinja` use Jinja templating to fill in values from your input
- **Dev container support** — includes `.devcontainer/` configuration so you can open a freshly generated project in a reproducible Docker-based dev environment if you use VS Code / Codespaces
- **Tooling baked in** — support for your preferred dependency manager, linting (Black, isort, flake/ruff), testing (pytest), and pre-commit hooks, all wired in from day one
- **Evolvable** — you can update the template over time and apply those updates to existing repos using Copier’s “upgrade” capabilities

---

## How to Use

1. Install Copier (e.g. `pip install copier`)
2. Run:

    ```bash
    copier copy <template-repo-url> my-project
    ```

3. Answer prompts (project_name, project_slug, include_ci, etc.)
4. Enter the generated project:

    ```bash
    cd my-project
    ```

5. Run initial setup (e.g. install dependencies, enable pre-commit hooks, open in dev container)
6. Start coding!

---

## Directory & File Layout

| Path                             | Purpose                                            |
| -------------------------------- | -------------------------------------------------- |
| `src/{{ project_slug }}/`        | Main Python package / module code                  |
| `tests/`                         | Test files (pytest)                                |
| `pyproject.toml.jinja`           | Template for project dependencies & metadata       |
| `.pre-commit-config.yaml.jinja`  | Pre-commit hook definitions                        |
| `.github/workflows/ci.yml.jinja` | Template for CI workflow                           |
| `.devcontainer/`                 | Configuration for Docker dev container (optional)  |
| `copier.yaml`                    | Defines template questions, defaults, and excludes |

---

## Customization & Extension

- **Add more questions**: You can expand `copier.yaml` with more prompts (e.g. “database engine?”, “use FastAPI?”)
- **Branch-based variants**: You can maintain branches for different templates (e.g. `fastapi-template`, `library-template`)
- **Continuous updates**: Use `copier update` from within an existing project (if configured) to adopt changes from the template
- **Conditional files**: Use Jinja logic in your template files to include/exclude parts (e.g. only include `ci.yml` if `include_ci` is true)

---

## License

MIT License
