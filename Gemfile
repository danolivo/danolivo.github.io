source "https://rubygems.org"

# Built with plain Jekyll 4 (not the `github-pages` gem, which pins Jekyll 3.10
# and refuses to install on Ruby >= 4). Deployment goes through GitHub Actions,
# see .github/workflows/pages.yml.
gem "jekyll", "~> 4.4"

group :jekyll_plugins do
  gem "jekyll-seo-tag", "~> 2.9"
  gem "jekyll-sitemap", "~> 1.4"
  # Feeds <lastmod> into the sitemap from git history, so crawlers get a
  # freshness signal. Requires full history at build time (fetch-depth: 0).
  gem "jekyll-last-modified-at", "~> 1.3"
end

gem "webrick", "~> 1.9"
