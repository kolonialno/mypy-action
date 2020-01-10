# Mypy action

Run Mypy and add annotate code with errors.

## Inputs

### `max-errors`

**Required** Max errors before reporting the check as failed

### `github-token`

**Required** A GitHub API token used to authenticate against the GitHub API

### `paths`

**Required** An optional space separated list of paths to run Mypy on

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
