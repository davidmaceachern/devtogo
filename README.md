<div align="center">
  👩🏽‍💻🎒
</div>

<h1 align="center">
  devtogo
</h1>

<p align="center">
    a dev.to tool for the road
</p>

<div align="center">
  <a href="https://github.com/softprops/devtogo/actions">
    <img src="https://github.com/softprops/devtogo/workflows/Main/badge.svg"/>
  </a>
  <a href="https://crates.io/crates/devtogo">
    <img src="http://meritbadge.herokuapp.com/devtogo"/>
  </a>
  <a href="LICENSE">
    <img src="https://img.shields.io/badge/license-MIT-brightgreen.svg"/>
  </a>
</div>

<br />

## install


### Via homebrew (osx)

```sh
$ brew install softprops/tools/devtogo
```

### Via cargo

```sh
$ cargo install devtogo
```

### Via GitHub Releases

```sh
$ cd $HOME/bin
$ curl -L "https://github.com/softprops/devtogo/releases/download/v0.0.1/devtogo-$(uname -s)-$(uname -m).tar.gz" \
  | tar -xz -C ~/bin
```

## usage

devtogo is a cli primarily focused on publishing offline markdown files to [dev.to](https://dev.to/).

The most basic usage is to run the program inside the directory containing content

```sh
$ devtogo
```

This will scan the current working directory for articles: markdown documents containing frontmatter describing metadata about the article. devtogo uses the `title` frontmatter field as a unique identifier to compare existing remote content. 

When it can't resolve an article by title it uploads it. When it can, it compares content and uploads local copy if the content of the local copy differs.

> you can use the `published` frontmatter to indicate if and when an article should be published
  by default articles are saved as drafts only you can see. Setting published to true will publish articles.
  If you do this by accident you can set published back to false to unpublish an article if needed

To be more explicit you can provide a source argument which provides a path where content
is stored.

```sh
$ devtogo --source path/to/content
```

Doug Tangren (softprops) 2020