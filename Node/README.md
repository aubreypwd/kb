# NODE

## How to bump `package.*` versions using `npm version` w/ out a tag in Git

```bash
npm version --no-git-tag-version <version>
```

This will bump the versions in `package.*` but will not add e.g. `vx.x.x` tag and push to Git.
