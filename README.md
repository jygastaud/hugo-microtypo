# Hugo Microtypo

That project is a try to build a Hugo module by porting [Jekyll Microtypo](https://github.com/borisschapira/jekyll-microtypo)


## Requirements

Git
Hugo > v0.56.0
go >= 1.12

## Installation

1. (Optional) If your hugo site is not already a Go module, initialize it with `go mod init` and the URL of your repository at the root of your project:

`hugo init github.com/username/repository`

It should create a `go.mod` file.

2. Add the module to your Hugo configuration file:

TOML example:

```toml
[module]

  [[module.imports]]
      path="github.com/jygastaud/hugo-microtypo/microtypo"
      disable=false
```

YAML example:
```yaml
module:
  imports:
    - path: github.com/jygastaud/hugo-microtypo/microtypo
      disable: false
```

3. Import the module

```
hugo mod get github.com/jygastaud/hugo-microtypo/microtypo
```

## Usage

* Replace any `{{ .Content }}` call by `{{ partial "content.html" . }}`
* Rebuild your site and you're done :tada:

## Contribute

Note that we can not guarrenty any maintenance of that plugin (yet) but we will do our best.

Be sure that we would more than happy to review any pull request.

If you need to work locally on the module, you can add that line at the end of your `go.mod` file:

```
replace github.com/jygastaud/hugo-microtypo/microtypo => /<your-path>/hugo-microtypo/microtypo
```
