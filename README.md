# Chirpy

A minimal, sidebar, responsive web design Jekyll theme, focusing on text presentation, aim to help you easily record and share your knowledge. [Live Demo »](https://chirpy.cotes.info)

[![Devices Mockup](https://raw.githubusercontent.com/cotes2020/jekyll-theme-chirpy/master/assets/img/sample/devices-mockup.png)](https://chirpy.cotes.info)

## Installing

### Prerequisites

Follow the [Jekyll Docs](https://jekyllrb.com/docs/installation/) to complete the installtion of basic environment (`Ruby `, `RubyGems` and `Bundler`). 

### Jekyll Plugins

[Fork **Chirpy** from GitHub](https://github.com/cotes2020/jekyll-theme-chirpy/fork), then clone your forked repo to local:

```console
$ git clone git@github.com:USER/jekyll-theme-chirpy.git -b master
```

## Usage

### Directory Structure

The main files and related brief introductions are listed below.

```sh
jekyll-theme-chirpy/

├── _includes      
├── _layouts
├── _posts          # posts stay here
├── _scripts
├── assets      
├── tabs
│   └── about.md    # the ABOUT page
├── 404.html
├── Gemfile
├── LICENSE
├── README.md
├── _config.yml     # configuration file
├── tools           # script tools
├── feed.xml
├── index.html
├── robots.txt
└── sitemap.xml
```

### Configuration

Generally, go to `_config.yml` and configure the variables as needed. Some of them are typical options:

* `url`
	
	Set to your website url and there should be no slash symbol at the tail. Format: `<protocol>://<domain>`.


* `avatar`
    
    It defines the image file location of avatar. The sample image is `/assets/img/sample/avatar.jpg`, and should be replaced by your own one(a square image). Notice that a huge image file will increase the load time of your site, so keep your avatar image size as samll as possible(may be *<https://tinypng.com/>* will help).

* `timezone`

    To ensure that the posts' release date matches the city you live in, please modify the field `timezone` correctly. A list of all available values can be found on [TimezoneConverter](http://www.timezoneconverter.com/cgi-bin/findzone/findzone) or [Wikipedia](https://en.wikipedia.org/wiki/List_of_tz_database_time_zones).

* `theme_mode`
  
	There are three options for the theme color scheme:
	
	- **dual** 	- The default color scheme will follow the system settings, but if the system does not support dark mode, or the browser does not support `Media Queries Level 5`, the theme will be displayed as `light` mode by default. Anyway, the bottom left corner of the Sidebar will provide a button for users to switch color schemes.

	- **dark**	- Always show dark mode.
	- **light**	- Always show light mode.


###  Run Locally

You may want to preview the site content before publishing, so just run the script tool:

```terminal
$ bash tools/run.sh
```

*Windows:* After installing `gem install jekyll bundler`
```terminal
>> bundle exec jekyll serve
```

Open a modern brower and visit at <http://localhost:4000>.

Few days later, you may find that the file modification(e.g. edits to a post) does not refresh in real time by using `run.sh`. Don't worry, the advanced option `-r` (or `--realtime`) will solve this problem, but it requires [**fswatch**](http://emcrisostomo.github.io/fswatch/) to be installed on your machine. Type `-h` for more information.

###  Deploying to GitHub Pages

Before the deployment begins, checkout the file `_config.yml` and make sure that the `url` has been configured. What's more, if you prefer the [Project site on GitHub](https://help.github.com/en/github/working-with-github-pages/about-github-pages#types-of-github-pages-sites) and also use the default domain `<username>.github.io`, remember to change the `baseurl` to your project name that starting with a slash. For example, `/project`.

#### Option: Build Locally

For security reasons, GitHub Pages runs on `safe` mode, which means the third-party Jekyll plugins or custom scripts won't work. If you want to use any another plugins that not in the [whitelist](https://pages.github.com/versions/), **you have to generate the site locally rather than on GitHub Pages**.


#### Finishing work

No matter which way you choose to deploy the website on GitHub, please enforce the `HTTPS` for it. See official docs: [Configuring a publishing source for your GitHub Pages site](https://help.github.com/en/github/working-with-github-pages/securing-your-github-pages-site-with-https).


### Documentation

For more details and the better reading experience, please check out the [tutorial in demo site](https://chirpy.cotes.info/categories/tutorial/). In the meanwhile, a copy of the tutorial is also available on the [Wiki](https://github.com/cotes2020/jekyll-theme-chirpy/wiki).

## Contributing

The old saying, "Two heads are better than one." Consequently, welcome to report bugs, improve code quality or submit a new feature. For more information, see [contributing guidelines](.github/CONTRIBUTING.md).


## Credits

This theme is mainly built with [Jekyll](https://jekyllrb.com/) ecosystem, [Bootstrap](https://getbootstrap.com/), [Font Awesome](https://fontawesome.com/) and some other wonderful tools(their copyright information can be found in the relevant files).

:tada:Thanks to all the volunteers who contributed to this project, their GitHub IDs are on [this list](https://github.com/cotes2020/jekyll-theme-chirpy/graphs/contributors). Also, I won't forget those guys who submitted the issues or unmerged PR because they reported bugs, shared ideas or inspired me to write more readable documentation.


## License

This work is published under [MIT](https://github.com/cotes2020/jekyll-theme-chirpy/blob/master/LICENSE) License.