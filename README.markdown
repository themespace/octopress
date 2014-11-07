## About

This is a clone of the [Octopress][] static site generator including a script functionality, which maintainers can use to publish *Themespace* theme previews.

[Octopress]: https://github.com/imathis/octopress

## Currently Included Themes

- [Whitespace][] ([Preview](http://themespace.github.io/whitespace/))
- [Koenigspress][] ([Preview](http://themespace.github.io/Koenigspress/))

[Whitespace]: https://github.com/lucaslew/whitespace
[Koenigspress]: https://github.com/TheChymera/Koenigspress

## Usage

Theme maintainers can publish an up-to-date standard-content preview of their theme by simply running the following from within a local clone of our repository:

```
git clean -f -d
./script/setup <theme-author-account> <theme-name>
rake install[<theme-name>]
rake gen_deploy
```

####It is important to note that:

* This *currently* only works with themes hosted on GitHub.
* To publish a preview, the theme in question needs first be cloned on Themespace as `themespace/<theme-name>`.
* To publish to Themespace (the `rake gen_deploy` part) you need to have push access to our theme clone.

*We are happy to assist maintainers with the latter two points, and we liberally accord push access to theme authors.*

## Script Summary

When creating a new theme preview - by running `script/setup <theme-author-account> <theme-name>` - the following files are modified:

- [Rakefile](Rakefile):
    ```
    public_dir: public/<theme-name>
    deploy_branch: gh-pages
    deploy_default: push
    deploy_dir: _deploy_<theme-name>
    ```

- [config.rb](config.rb):
    ```
    http_path: /<theme-name>/
    http_images_path: /<theme-name>/images
    http_fonts_path: /<theme-name>/fonts
    css_dir: public/<theme-name>/stylesheets
    ```

- [_config.yml](_config.yml):
    ```
    destination: public/<theme-name>
    subscribe_rss: /<theme-name>/atom.xml
    root: /<theme-name>
    url: http://themespace.github.io/<theme-name>
    author: Themespace
    github_user: themespace
    ```

Previews are deployed to the `gh-pages` branches of our respective theme repository clones (e.g. `github.com/themespace/<theme-name>`).

## Licenses

- [Octopress](https://github.com/imathis/octopress#license)
- [Whitespace](https://github.com/lucaslew/whitespace#license)
- [Koenigspress](https://github.com/TheChymera/Koenigspress#meta)
