# Mypy action

Run Mypy and annotate code with errors.

## Inputs

### `max-errors`

**Required** Max errors before reporting the check as failed

### `github-token`

**Required** A GitHub API token used to authenticate against the GitHub API

### `paths`

**Required** An optional space separated list of paths to run Mypy on

### `diff-against-branch`

Specify a branch that will be used as a reference branch. Only .py files that
have been modified from that branch will be checked. If this option is
specified the `paths` option is ignored.

## Usage

```yaml
uses: kolonialno/mypy-action@v1
with:
  github-token: ${{ secrets.GITHUB_TOKEN }}
  max-errors: 0
  paths: some_path another_path
```

## Code in Master

Install the dependencies  
```bash
$ yarn install
```


## Package for distribution

To build the production version used by the GitHub Actions runner, please run
this command and commit the modified files in the `dist/` directory:

```bash
yarn run package
```

## Release a new version

```sh
git checkout -b releases/v1
git commit -a -m "Release v1.0.0"
git push origin releases/v1
git tag v1.0.0
git push origin v1.0.0
# Remember to also update the major version tag
git tag -f v1 -m "Update v1 tag"
git push origin v1 --force
```
