# awscommunitynordics.org

This is the repository of the website [awscommunitynordics.org](https://awscommunitynordics.org/).

It is hosted directly from this repository in Netflify.

# Running development environment locally

If you are developing major changes, it makes sense to test and validate the changes locally using Jekyll installation. If you are doing small changes, like fixing a typo, those can be done directly to the repository witn no need to install anything locally, though it is highly advisable, so you won't break anything in production.

## Installation

### Prerequisites

Install [Ruby and Bundler](https://help.github.com/articles/setting-up-your-github-pages-site-locally-with-jekyll/) if you don't have them already.

### Install jekyll locally on your computer
This Netlify site is configured to be published from the `/docs` folder on the `master` branch. Change directory to that folder `cd docs`.

Install Jekyll gem and other [dependencies](docs/Gemfile):

```
bundle install
```

If your user account isn't allowed to install to the system RubyGems you can run `bundle install --path vendor/bundle` to install the gems locally.

For MacOS install, you might want to check the [Jekyll documentation](https://jekyllrb.com/docs/installation/macos/).

## Serve

To preview the Jekyll site locally run:

```
bundle exec jekyll serve
```

### Run jekyll via docker
```
docker run --rm   --volume="$PWD/docs:/srv/jekyll:Z" --name jekyll -p 127.0.0.1:4000:4000  -it jekyll/jekyll:3  jekyll serve -H 0.0.0.0 --draft

```

### When jekyll is running
Then, load [http://localhost:4000/](http://localhost:4000/) in your browser.
