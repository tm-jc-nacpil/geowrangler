# How to make a release

## Bumping the version

Run the following. Use `<part>` = 0, 1, 2 for major, minor or patch depending on the release. See https://nbdev.fast.ai/api/release.html#bump-version for more details

```
nbdev_bump_version --part <part>
```

## Publishing

You will need to have an API token for [PyPi](https://pypi.org/) (or [TestPyPi](https://test.pypi.org/)). Ask the current project owners for access. 

Set your `~/.pypirc` file as follows.
```
[distutils]
index-servers =
    pypi
    testpypi

[pypi]
username = __token__
password = <PyPI token>

[testpypi]
username = __token__
password = <TestPyPI token>
```
Run the following to publish to PyPi (or TestPypi). 
The `<REPOSITORY>` value is either `pypi` or `testpypi`.
```
./scripts/publish2pypi.sh <REPOSITORY>
```

## Submitting

Create a PR and tag it as the release version. The tag should be in the format `vX.Y.Z` where `X.Y.Z` is the major, minor and patch version numbers. 
