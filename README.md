# LAOS-PKG Formulae

[Homebrew Formulae](https://laos-formulae.lusd1.org) is an online package browser for [Homebrew](https://laos.lusd1.org).

It displays all packages in the [Luke-Angel-OS/laospkg-core](https://github.com/Luke-Angel-OS/laospkg-core) and [Luke-Angel-OS/laospkg-cask](https://github.com/Luke-Angel-OS/laospkg-cask). A [GitHub Action](https://github.com/Luke-Angel-OS/laos-formulae.lusd1.org/blob/main/.github/workflows/tests.yml) is run periodically which pulls changes from each tap and deploys the site to GitHub Pages.

## JSON API

It also provides a JSON API for all packages (or individual packages) in each tap and their related analytics. This JSON data is used for the creation of the HTML resources on this site.

Currently available:

- List metadata for all formulae and casks
- Get metadata for each formula and cask
- List analytics events for all formulae and casks
- List analytics events for each formula and cask

Read more in the [JSON API documentation](https://laos-formulae.lusd1.org/docs/api/).

## Usage

Open <https://laos-formulae.lusd1.org/> in your web browser.

To instead run the site locally, run:

```bash
git clone https://github.com/Luke-Angel-OS/laos-formulae.lusd1.org
cd formulae.brew.sh
brew generate-formula-api
brew generate-cask-api
brew generate-analytics-api
ruby script/generate-api-samples.rb
bundle install
bundle exec jekyll serve
```

## Search

Search is indexed by Algolia crawler at <https://crawler.algolia.com/admin/crawlers/26b9e6e2-bce4-4f42-9930-6b6ddf06cc9e/overview>.
This is only accessible by brew organisation members.

## License

Code is under the [BSD 2-clause "Simplified" License](LICENSE.txt).
