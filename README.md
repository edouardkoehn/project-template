# Python Project Template

This is a template repository for starting a new Python project.

It uses [Poetry](https://python-poetry.org/) for dependency management and versioning. Basic [CI/CD](https://github.com/resources/articles/devops/ci-cd) is set up using [GitHub Actions](https://github.com/features/actions). The testing framework is [pytest](https://docs.pytest.org/en/stable/), and we use [pre-commit](https://pre-commit.com/) to enforce code formatting and maintain code quality.

The CI pipeline installs the project using the `pyproject.toml` file and automatically runs the included unit tests. We **strongly** suggest that users use [miniconda](https://www.anaconda.com/docs/getting-started/miniconda/main) to set up its virtual environment.

## Getting Started

1. Click **"Use this template"** to create your own repository from this template.
2. Follow the **"Instal your repo locally"** instructions provided in the repository to get started.


## Instal your repo locally
- Clone the repo

```bash
git clone https://github.com/edouardkoehn/XX.git
```
- Create your virtual env using conda
```bash
conda create -n projectName python=3.10
conda activate projectName
```
- Install poetry
```bash
pip install poetry
```
- Install the module and set up the precommit
```bash
poetry install --all-groups
poetry run pre-commit install
poetry env info
```

## Managing Dependencies

Poetry is a powerful tool that helps you manage and update project dependencies with ease. It allows you to automatically track and specify the required versions of dependencies in your project.

### Adding a Dependency

To add a dependency with Poetry, such as `numpy`, simply run the following command:
```bash
poetry install numpy
```
This command will not only install `numpy` but also automatically update the `pyproject.toml` file to reflect the new dependency.

### Grouping Dependencies
Poetry also enables you to group dependencies based on their function, which is useful for creating lighter production requirements or separating dependencies used for development or testing.

For example, to add `pytest` as a development dependency (for testing), you can use the `--group` flag:
```bash
poetry add pytest --group test
```

This will install `pytest` and categorize it under the `test` group in the `pyproject.toml` file, ensuring that only the necessary dependencies are included in production.

[More info about managing dependencies with Poetry](https://python-poetry.org/docs/managing-dependencies/#adding-a-dependency-to-a-group)

---

## Pre-commit Hooks

Pre-commit hooks are small programs that run automatically when you perform a `git commit`. These hooks are designed to check your code for various issues such as formatting, missing imports, and other common problems before allowing the commit to go through.

If any of the checks fail, the commit will be rejected, and you will need to resolve the issues before trying again. This ensures that code quality is maintained and that commits are always in a consistent state.

All the used config are defined in the `.pre-commit-config.yaml` file.

### Good Practices with Pre-commit:

1. **Commit Regularly**: It's a good practice to commit your changes frequently to avoid large, unwieldy commits. This helps you keep track of your changes and ensures that the pre-commit hooks run regularly to catch errors early.

2. **Don't Commit in a Rush**: Never commit when you're in a rush. If you skip fixing issues that the pre-commit hooks flag, you could introduce problems into the project. Always take the time to address issues reported by the pre-commit hooks to maintain high-quality code.

By following these practices and using pre-commit hooks, you ensure that your commits meet a high standard of quality, making it easier to maintain the project in the long run.

For more details on setting up and using pre-commit hooks, you can visit the [pre-commit official website](https://pre-commit.com/).
