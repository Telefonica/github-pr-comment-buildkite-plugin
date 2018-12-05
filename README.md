# github-pr-comment-buildkite-plugin
buildkite plugin to post a comment in a PR

## Example


```yml
steps:
  env:
    - GITHUB_TOKEN
  plugins:
    - telefonica/github-pr-comment#0.0.1:
        comment: |
          Comment to PRs for ${BUILDKITE_COMMIT}

```