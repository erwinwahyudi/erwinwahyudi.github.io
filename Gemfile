# source 'https://rubygems.org'
# gem 'github-pages', group: :jekyll_plugins
source 'https://rubygems.org'

require 'json'
require 'open-uri'
versions = JSON.parse(open('https://pages.github.com/versions.json').read)

gem 'github-pages', versions['github-pages']
gem 'jekyll-paginate'
gem 'jemoji'
gem 'jekyll-sitemap'
gem 'jekyll-feed'
gem 'webrick'
