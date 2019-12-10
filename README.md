# Hugo Microtypo

That project is a try to build a Hugo module by porting [Jekyll Microtypo](https://github.com/borisschapira/jekyll-microtypo)

## Installation

* Add the module to your configuration

TOML example

```toml
[module]

  [[module.imports]]
      path="github.com/jygastaud/hugo-microtypo/microtypo"
      disable=false
```

* Import the module

```
hugo mod get github.com/jygastaud/hugo-microtypo/microtypo
```

## Usage

* Replace any `{{ .Content }}` call by `{{ partial "content.html" . }}`
* Rebuild your site

## Contribute

Note that we can not guarrenty any maintenance of that plugin (yet) but we will do our best.

Be sure that we would more than happy to review any pull request.

If you need to work locally on the module, you can add that line at the end of your `go.mod` file:

```
replace github.com/jygastaud/hugo-microtypo/microtypo => /<your-path>/hugo-microtypo/microtypo
```
