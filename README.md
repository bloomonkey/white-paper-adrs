# ADRs

**ADRs** is a theme for Jekyll.
It is intended for keeping records of decisions you made about software architecture.
It is based on the beautiful and simple [White Paper](http://vinitkumar.me/white-paper/).

## How to use ADRs

Fork the repo to your account.

Change these entries in the `_config.yml` file:

- [ ] `url`
- [ ] `owner.name`
- [ ] `owner.github`


This will make sure that the path of CSS is correct and the theme loads correctly.

```yml
master_repo: false
url: "<username>.github.io"
rtl: false  # change to true if posts is in Arabic/other Right to left language.
```

## Installation

### Local Development

This theme requires you to install couple of tools first to setup jekyll locally.

```$
git clone git@github.com:vinitkumar/white-paper.git

# If you have ruby installed.
gem install jekyll bundler

# If you have node installed.
npm install
sudo npm install -g grunt-cli  #to get the task runner for grunt.
bundle install
jekyll serve

# on running the serve script, the site will be live on
http://127.0.0.1:4000
```
This theme uses grunt to concat & minify the css for best performance. In order to prepare the css build. Run `grunt`
It will create a main.min.css file in the css folder.

### Switch Syntax Highlighting.

This theme also provides syntax highlighting in different theme. Inside css folder, there is a syntax folder.

```$
.
├── emacs.css
├── github.css
├── monokai.css
├── native.css
├── syntax.css
└── vim.css

```

Now in the gruntfiles.js

```js
concat: {
  dist: {
    src: [
      'css/base.css',
      'css/sytax/emacs.css', // change this to another theme if you prefer, like vim.css and run grunt
      'css/octicons.css'
    ],
    dest: 'css/<%= pkg.name %>.add.css'
  }
}
```

## License
* see [LICENSE](LICENSE) file
