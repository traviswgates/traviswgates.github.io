---
title: Manually Releasing a Python Package -- From Build to GitHub Release
feature_image: "/assets/images/bench-blur.jpg"
excerpt: "From Python build and twine to GitHub tags and releases; understand the steps involved in manually publishing a Python package to PyPI."
categories:
- Guide
---

# Manually Releasing a Python Package with GitHub

So; you've been writing some python code, and you're ready to bundle it into a package.

You've read about Python Package Structures.

Maybe you've got some Unit Tests.

Maybe you've even published a previous version of your package to Test PyPI or PyPI and didn't take perfect notes last time.

Hopefully this guide will help you out!

## Building and Uploading to Test PyPI and PyPI

First, you'll need the python packages `build` and `twine`. Install them with pip:

```
pip install build twine
```

>build constructs a Python package
>twine uploads a Python package to PyPI or TestPyPI

The hypothetical Python Package `foo` uses a `pyproject.toml` file and a `setup.cfg` file.

Build it with the `build` package. It may take a while.
`python -m build`

Default output is placed in `./dist/`

To upload to Test PyPI, use twine's `-r`:
`twine upload -r testpypi dist/*`

Doing this will prompt you for your Test PyPI credentials at the shell.

`python -m pip install -i https://test.pypi.org/{{packagename}}`

Install your package from Test PyPI; note that failure may occur due to missing dependencies.

Upload to PyPI. This will prompt you for credentials at the shell.
`twine upload dist/*`

## Creating a Release in GitHub
Tags are a clean way to manage releases.

1. After pushing to 'main', create a tag:
`git tag -a v0.0.2 -m "version 0.0.2"`

2. Push the tag:
`git push origin v0.0.2`

3. Create a release on github
Best way I've found is **Code > Tags > Releases > Draft New Release**, then select your newly created tag; be sure to upload your distributables to github too.
