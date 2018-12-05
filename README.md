# github-pr-comment-buildkite-plugin
buildkite plugin to post a comment in a PR

## Example

```yml
steps:
  plugins:
    - telefonica/github-pr-comment#0.0.2:
        comment: Some text
        commit: ${BUILDKITE_COMMIT} # Optional, defaults to $BUILDKITE_COMMIT
        repo: ${BUILDKITE_REPO} # Optional, defaults to $BUILDKITE_REPO (format git@github.com:user/repo.git)
```

## Authentication
The plugin needs an env var called [`GITHUB_TOKEN` with `repo` access](https://github.com/settings/tokens) to post comments
