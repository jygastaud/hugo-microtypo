# Hugo Microtypo

That project is a try to build a Hugo module by porting [Jekyll Microtypo](https://github.com/borisschapira/jekyll-microtypo)


## Requirements

* Git
* Hugo > v0.56.0
* go >= 1.12

## Installation

1. (Optional) If your hugo site is not already a Go module, initialize it with `hugo mod init` and the URL of your repository at the root of your project:

`hugo mod init github.com/username/repository`

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

### Simple case: You want to apply microtypo to .Content variable

* Replace any `{{ .Content }}` call by `{{ partial "content.html" . }}`
* Rebuild your site and you're done :tada:

### Advanced case: You want to apply microtypo to any variable with content inside

For that case, you can use the `microtypo.html` partial.

Let say you want to apply microtypo to the `.Summary` variable, you will have to  
replace `{{ .Summary }}` call by `{{ partial "microtypo.html" (dict "Content" .Summary "CurrentLang" .Site.Language.Lang) }}`.

To make it works for any other variable, you just have to replace `.Summary` variable in the `dict` function.

`"Content"` key and `"CurrentLang" .Site.Language.Lang` must be keep.


## Contribute

Note that we can not guarrenty any maintenance of that plugin (yet) but we will do our best.

Be sure that we would more than happy to review any pull request.

If you need to work locally on the module, you can add that line at the end of your `go.mod` file:

```
replace github.com/jygastaud/hugo-microtypo/microtypo => /<your-path>/hugo-microtypo/microtypo
```
