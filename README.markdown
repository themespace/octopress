## About

This is clone of [Octopress][] containing our themes for showcase.

[Octopress]: https://github.com/imathis/octopress

## Themes

- [Whitespace][] ([Preview](http://themespace.github.io/whitespace/))

[Whitespace]: https://github.com/lucaslew/whitespace

## How to Setup Theme

To setup the theme which is called `<theme>`, run `script/setup <theme>`. Then it modifies files below.

- [Rakefile](Rakefile):
    ```
    public_dir: public/<theme>
    deploy_branch: gh-pages
    deploy_default: push
    deploy_dir: _deploy_<theme>
    ```

- [config.rb](config.rb):
    ```
    http_path: /<theme>/
    http_images_path: /<theme>/images
    http_fonts_path: /<theme>/fonts
    css_dir: public/<theme>/stylesheets
    ```

- [_config.yml](_config.yml):
    ```
    destination: public/<theme>
    subscribe_rss: /<theme>/atom.xml
    root: /<theme>
    url: http://themespace.github.io/<theme>
    ```

Then you can deploy to `gh-pages` branch of `github.com/themespace/<theme>` repository.

If you have deployed sites from another machine already, you have to clone it to `_deploy_<theme>`:

``` sh
git clone -b gh-pages git@github.com:themespace/<theme> _deploy_<theme>
```

## License

- [Octopress](https://github.com/imathis/octopress#license)
- [Whitespace](https://github.com/lucaslew/whitespace#license)
