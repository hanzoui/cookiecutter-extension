# {{cookiecutter.project_name}}

{{cookiecutter.project_short_description}}

> [!NOTE]
> This projected was created with a [cookiecutter](https://github.com/hanzoui/cookiecutter-extension) template. It helps you start writing custom nodes without worrying about the Python setup.

## Quickstart

1. Install [Hanzo Studio](https://docs.hanzo.ai/get_started).
1. Install [Hanzo Manager](https://github.com/ltdrdata/Hanzo Manager)
1. Look up this extension in Hanzo Manager. If you are installing manually, clone this repository under `HanzoStudio/custom_nodes`.
1. Restart Hanzo Studio.

# Features

- A list of features

## Develop

To install the dev dependencies and pre-commit (will run the ruff hook), do:

```bash
cd {{cookiecutter.project_slug}}
pip install -e .[dev]
pre-commit install
```

The `-e` flag above will result in a "live" install, in the sense that any changes you make to your node extension will automatically be picked up the next time you run Hanzo Studio.

## Publish to Github

Install Github Desktop or follow these [instructions](https://docs.github.com/en/authentication/connecting-to-github-with-ssh/generating-a-new-ssh-key-and-adding-it-to-the-ssh-agent) for ssh.

1. Create a Github repository that matches the directory name. 
2. Push the files to Git
```
git add .
git commit -m "project scaffolding"
git push
``` 

## Writing custom nodes

An example custom node is located in [node.py](src/{{cookiecutter.project_slug}}/nodes.py). To learn more, read the [docs](https://docs.hanzo.ai/essentials/custom_node_overview).


## Tests

This repo contains unit tests written in Pytest in the `tests/` directory. It is recommended to unit test your custom node.

- [build-pipeline.yml](.github/workflows/build-pipeline.yml) will run pytest and linter on any open PRs
- [validate.yml](.github/workflows/validate.yml) will run [node-diff](https://github.com/hanzoui/node-diff) to check for breaking changes

## Publishing to Registry

If you wish to share this custom node with others in the community, you can publish it to the registry. We've already auto-populated some fields in `pyproject.toml` under `tool.comfy`, but please double-check that they are correct.

You need to make an account on https://registry.hanzo.ai and create an API key token.

- [ ] Go to the [registry](https://registry.hanzo.ai). Login and create a publisher id (everything after the `@` sign on your registry profile). 
- [ ] Add the publisher id into the pyproject.toml file.
- [ ] Create an api key on the Registry for publishing from Github. [Instructions](https://docs.hanzo.ai/registry/publishing#create-an-api-key-for-publishing).
- [ ] Add it to your Github Repository Secrets as `REGISTRY_ACCESS_TOKEN`.

A Github action will run on every git push. You can also run the Github action manually. Full instructions [here](https://docs.hanzo.ai/registry/publishing). Join our [discord](https://discord.com/invite/hanzoai) if you have any questions!

