# github-pr-comment-buildkite-plugin
buildkite plugin to post a comment in a PR

## Examples
You can post basic string literal comments very easily:
```yml
steps:
  plugins:
    - ssh://git@github.com/fanduel/github-pr-comment-buildkite-plugin.git#v1.0.0:
        comment: Some text
        pr: ${BUILDKITE_PULL_REQUEST} # Optional, PR Number to add the comment
        repo: ${BUILDKITE_PULL_REQUEST_REPO} # Optional, format git://github.com:user/repo.git)
```

By setting the `dynamic` property to `true`, we can pass the name of an environment variable whose value will be used for the comment body.
```yml
steps:
  - label: Set some meta-data
    command: buildkite-agent meta-data set username ${BUILDKITE_BUILD_CREATOR_EMAIL}
    # The meta-data key "username" and its value get exported as METAENV_USERNAME via the metaenv plugin in the next step

  - plugins:
      - ssh://git@github.com/fanduel/metaenv-buildkite-plugin.git#v1.0.0
      - ssh://git@github.com/fanduel/github-pr-comment-buildkite-plugin.git#v1.0.0:
          comment: METAENV_USERNAME
          dynamic: true
```
