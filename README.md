# github-pr-comment-buildkite-plugin
buildkite plugin to post a comment in a PR

## Example

```yml
steps:
  plugins:
    - telefonica/github-pr-comment#0.0.5:
        comment: Some text
        pr: ${BUILDKITE_PULL_REQUEST} # Optional, PR Number to add the comment
        repo: ${BUILDKITE_PULL_REQUEST_REPO} # Optional, format git://github.com:user/repo.git)
```

## Authentication
The plugin needs an env var called [`GITHUB_TOKEN` with `repo` access](https://github.com/settings/tokens) to post comments
