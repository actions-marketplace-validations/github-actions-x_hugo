# hugo

Use [Hugo](https://gohugo.io) with Github Actions

## Usage

Build Hugo site and push to GitHub. See [my blog](https://github.com/rusnasonov/blog)

```yaml
name: publish

on:
  push:
    branches:
    - master
    
jobs:
  build:
    runs-on: ubuntu-latest
    steps:
    - name: checkout
      uses: actions/checkout@master
    - name: build
      uses: github-actions-x/hugo@master
    - name: push
      uses: github-actions-x/commit@master
      with:
        github_token: ${{ secrets.GITHUB_TOKEN }}
        push_branch: 'master'
        commit_message: 'publish'
```