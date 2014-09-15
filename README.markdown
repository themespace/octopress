## About

This is clone of [Octopress][] containing our themes for showcase.

[Octopress]: https://github.com/imathis/octopress

## Themes

- [Whitespace][] ([Preview](http://themespace.github.io/whitespace/))
- [Koenigspress][] ([Preview](http://themespace.github.io/Koenigspress/))

[Whitespace]: https://github.com/lucaslew/whitespace
[Koenigspress]: https://github.com/TheChymera/Koenigspress

## How to Setup Theme

To setup the theme which is written by `<theme-author-account>` and called `<theme-name>`, run `script/setup <theme-author-account> <theme-name>`. Then it modifies files below.

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

Then you can deploy to `gh-pages` branch of `github.com/themespace/<theme-name>` repository.

## Deploying

``` sh
git clean -f -d
./script/setup <theme-author-account> <theme-name>
rake install[<theme-name>]
rake gen_deploy
```

## License

- [Octopress](https://github.com/imathis/octopress#license)
- [Whitespace](https://github.com/lucaslew/whitespace#license)
- [Koenigspress](https://github.com/TheChymera/Koenigspress#meta)
