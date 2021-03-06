# Solidus JSON API

[![Circle CI](https://circleci.com/gh/wildcardlabs/solidus_json_api.svg?style=shield&circle-token=e2f6283b074ca9febcafab729d466ded2334300c)](https://circleci.com/gh/wildcardlabs/solidus_json_api)
[![Coverage Status](https://coveralls.io/repos/github/wildcardlabs/solidus_json_api/badge.svg?branch=master)](https://coveralls.io/github/wildcardlabs/solidus_json_api?branch=master)

A JSON API for Solidus.

Documentation: [http://solidusapi.wildcardlabs.com](http://solidusapi.wildcardlabs.com)

## Installation

Add solidus_json_api to your Gemfile:

```ruby
gem 'solidus_json_api', github: 'wildcardlabs/solidus_json_api'
```

## Road to 1.0

***
Please note that there actually has been a _lot_ of work done.
The lack of checked off boxes doesn't give this gem the respect it deserves.
***

There's several things blocking 1.0.
Below, you'll see a bullet list of requirements that are both specific to the app, the JSON API spec, and third parties.

- [ ] Manage permissions with CanCanCan.
- [ ] Add support for XML.
- [x] Add support for pagination.
  - [x] `page` keyword support for pagination.
  - [x] `links` document at the root for `self`, `next`, `prev`, `last`, and `first`.
- [ ] Add support for filtration.
  - [x] Be able to filter onto the main data object.
  - [ ] Be able to filter the included relationships.
- [ ] Provide JSON API specific error objects. Provide support for:
  - [ ] `id`
  - [ ] `links`
     - [ ] `about`
  - [x] `status`
  - [x] `code`
  - [x] `title`
  - [x] `detail`
  - [ ] `source`
    - [x] `pointer`
    - [ ] `parameter`
  - [x] `meta`
- [ ] Only accept data in the JSON API format.
- [ ] Respond with header `Content-Type: application/vnd.api+json`.
- [ ] Add support for sparse fieldsets.
- [ ] Add support for sorting.

| Resource         |  index  | create  |  show   | update  | destroy |
|------------------|:-------:|:-------:|:-------:|:-------:|:-------:|
| Adjustment       |   [ ]   |   [ ]   |   [ ]   |   [ ]   |   [ ]   |
| Address          |   [ ]   |   [ ]   |   [ ]   |   [ ]   |   [ ]   |
| Checkout         |   [ ]   |   [ ]   |   [ ]   |   [ ]   |   [ ]   |
| Country          |   [x]   |   [ ]   |   [x]   |   [ ]   |   [ ]   |
| Image            |   [x]   |   [ ]   |   [x]   |   [ ]   |   [ ]   |
| Line Item        |   [ ]   |   [x]   |   [ ]   |   [ ]   |   [ ]   |
| Option Type      |   [x]   |   [ ]   |   [x]   |   [ ]   |   [ ]   |
| Option Value     |   [x]   |   [ ]   |   [x]   |   [ ]   |   [ ]   |
| Order            |   [x]   |   [ ]   |   [x]   |   [ ]   |   [ ]   |
| Payment          |   [ ]   |   [ ]   |   [ ]   |   [ ]   |   [ ]   |
| Price            |   [x]   |   [ ]   |   [x]   |   [ ]   |   [ ]   |
| Product          |   [x]   |   [ ]   |   [x]   |   [ ]   |   [ ]   |
| Product Property |   [ ]   |   [ ]   |   [ ]   |   [ ]   |   [ ]   |
| Return Auth      |   [ ]   |   [ ]   |   [ ]   |   [ ]   |   [ ]   |
| Shipment         |   [ ]   |   [ ]   |   [ ]   |   [ ]   |   [ ]   |
| State            |   [x]   |   [ ]   |   [x]   |   [ ]   |   [ ]   |
| Stock Location   |   [ ]   |   [ ]   |   [ ]   |   [ ]   |   [ ]   |
| Stock Movement   |   [ ]   |   [ ]   |   [ ]   |   [ ]   |   [ ]   |
| Stock Item       |   [ ]   |   [ ]   |   [ ]   |   [ ]   |   [ ]   |
| Store            |   [ ]   |   [ ]   |   [ ]   |   [ ]   |   [ ]   |
| Store Credit     |   [ ]   |   [ ]   |   [ ]   |   [ ]   |   [ ]   |
| Tax Category     |   [ ]   |   [ ]   |   [ ]   |   [ ]   |   [ ]   |
| Tax Rate         |   [ ]   |   [ ]   |   [ ]   |   [ ]   |   [ ]   |
| Taxon            |   [x]   |   [ ]   |   [x]   |   [ ]   |   [ ]   |
| Taxonomy         |   [x]   |   [ ]   |   [x]   |   [ ]   |   [ ]   |
| User             |   [x]   |   [ ]   |   [x]   |   [ ]   |   [ ]   |
| Variant          |   [x]   |   [ ]   |   [x]   |   [ ]   |   [ ]   |
| Zone             |   [ ]   |   [ ]   |   [ ]   |   [ ]   |   [ ]   |

## Testing

First bundle your dependencies, then run `rake`. `rake` will default to building the dummy app if it does not exist, then it will run the specs.
The dummy app can be regenerated by using `rake test_app`.

```shell
bundle
bundle exec rake
```

Copyright &copy; 2015 Ben A. Morgan, released under the New BSD License
