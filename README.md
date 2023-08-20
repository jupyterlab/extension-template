# JupyterLab extension template

[![Github Actions Status](https://github.com/jupyterlab/extension-template/workflows/CI/badge.svg)](https://github.com/jupyterlab/extension-template/actions/workflows/main.yml)

A [copier](https://copier.readthedocs.io) template for creating
a JupyterLab extension. Four kinds of extension are supported:
- _frontend_: Pure frontend extension written in TypeScript.
- _mimerenderer_: MIME renderer extension.
- _server_: Extension with frontend (in TypeScript) and backend (in Python) parts.
- _theme_: Theme for JupyterLab (using CSS variables).

## Use the template to create extension

0. Pre-requisites

We strongly advice you to use conda package manager.
To do so, you can install [Miniconda](https://docs.conda.io/en/latest/miniconda.html).

Once you have it installed, open a _Anaconda Prompt_ (on Windows) or any shell
(on Linux and macOS) and execute the following commands:

```sh
conda config --add channels conda-forge
conda install -yc conda-forge mamba
```

The first one will give you access to the community driven package repository
[conda-forge](https://conda-forge.org/docs/user/introduction.html). And the
second will install a faster package manager than conda, [mamba](https://mamba.readthedocs.io).
It is fully compatible with _conda_ and uses the same command syntax.

1. Install copier and some plugins.

With `conda` / `mamba` (the two commands have the same API):

```sh
mamba install -c conda-forge "copier>=7,<8" jinja2-time
```

or

With `pip`:

```sh
pip install "copier~=7.2" jinja2-time "pydantic<2.0.0"
```

2. Create an extension directory and go to it.

```sh
mkdir myextension
cd myextension
```

3. Use copier to generate an extension, following the prompts to fill all required information.

```sh
copier copy https://github.com/jupyterlab/extension-template .
```

> If you use copier v8+, you will need to pass the flag `--UNSAFE` (see [documentation](https://copier.readthedocs.io/en/stable/configuring/#unsafe)).

<details><summary><em>How to use a template specific version</em></summary>

If you'd like to generate an extension for a older release, use the `--vcs-ref` option and give a tag or commit from this repository.

```sh
copier --vcs-ref v4.0.0 copy https://github.com/jupyterlab/extension-template .
```

> If you use copier v8+, you will need to pass the flag `--UNSAFE` (see [documentation](https://copier.readthedocs.io/en/stable/configuring/#unsafe)).

---

</details>

4. What's next

At this point, you repository has been [initialize with git](https://www.atlassian.com/git/tutorials/setting-up-a-repository) as code versioning tool and a development environment has been set up if you picked `conda` or `venv`. You should be all set. Open your preferred code editor and start coding.

> If you are using Visual Studio Code, you may be interested in the 
> [configuration template](https://github.com/jupyterlab/vscode-config-template) for JupyterLab extension.

> If you are looking for a template compatible with JupyterLab version prior to 4.0.0, look at 
> the [cookiecutter template](https://github.com/jupyterlab/extension-cookiecutter-ts) or the
> [mimerenderer template](https://github.com/jupyterlab/mimerender-cookiecutter-ts).

## Update an extension to the latest template version

> This only works with an older version of the _copier_ template. It does not work
> with an extension generated using the cookiecutter template. In that case, you
> could try to execute the script `python -m jupyterlab.upgrade_extension .` first.

Extension generated from the copier template can be [updated](https://copier.readthedocs.io/en/stable/updating/)
with a newer version of the template by executing the command:

```sh
copier update
```

> If you use copier v8+, you will need to pass the flag `--UNSAFE` (see [documentation](https://copier.readthedocs.io/en/stable/configuring/#unsafe)).

## A simple example

Your new extension includes a very simple example of a working extension. Use this example as a guide to build your own extension. Have a look at the [extension examples](https://github.com/jupyterlab/extension-examples) repository for more information on various JupyterLab features.
