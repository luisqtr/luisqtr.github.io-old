# Personal Webpge

<https://luisqtr.com> and <https://luiseduve.github.io/>

**Luis Quintero**

## Installation

*For Windows:* 

1. Install Ruby+DevKit [v2.6.9][Ruby] (with the dependencies requested in the MSYS prompt). 
2. Install the gems: `$ gem install jekyll bundler`
3. Install specific gems for project with bundler: `$ bundle install`

[Ruby]: https://github.com/oneclick/rubyinstaller2/releases/download/RubyInstaller-2.6.9-1/rubyinstaller-devkit-2.6.9-1-x64.exe

## Execution

Once the gems are installed, test locally instead of deploying on GitHub every change: 

1. Run `$ bundle exec jekyll serve`
2. Open a browser at <http://localhost:4000>

## Updating website

When finished editing, update the html for categories and tabs. Currently:

|categories|subcategory|tags|
|---|---|---|
|`notes, research, education`|`dev, writing, projects`|`XR, ML, physio, unity, python, others`|

1.  running in git bash `$ sh _scripts/sh/create_pages.sh`, or even `$ sh ./tools/build.sh` to generate the whole website.
2. Send to github: `git push`

## Other resources

- Jekyll template: <https://github.com/cotes2020/jekyll-theme-chirpy>
- Template for Academic purposes: <https://github.com/alshedivat/al-folio>

## License

This work is published under [MIT](https://github.com/cotes2020/jekyll-theme-chirpy/blob/master/LICENSE) License.