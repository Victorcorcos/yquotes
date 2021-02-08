# YQuotes

[![Gem Version](https://badge.fury.io/rb/yquotes.svg)](https://badge.fury.io/rb/yquotes)
[![Build Status](https://travis-ci.org/cpankaj/yquotes.svg?branch=master)](https://travis-ci.org/cpankaj/yquotes)

Get historical quotes from Yahoo Finance.


## Installation

Add this line to your application's Gemfile:

```ruby
gem 'yquotes'
```

And then execute:

	$ bundle config build.nokogiri --use-system-libraries
    $ bundle

Or install it yourself as:

	$ gem install nokogiri -- --use-system-libraries
    $ gem install yquotes

## Usage

1) Initial config

```rb
client = YQuotes::Client.new
ticker = 'TSLA' # For Example
```

2) Capturing stock quotes

```rb
df = client.get_quote(ticker, {
  period: 'm',
  start_date: '2017-01-02',
  end_date: '2017-03-31'
})
```

> OR

```rb
df = client.get_quote(ticker, {
  p: 'd',
  s: '2017-01-02',
  e: '2017-03-31'
})
```

where...

* period (p):
  * `'d'` => Day
  * `'w'` => Week
  * `'m'` => Month

* start_date (s):
  * Date in format: 'yyyy-mm-dd'

* end_date (e):
  * Date in format: 'yyyy-mm-dd'


## Development

After checking out the repo, run `bin/setup` to install dependencies. Then, run `rake spec` to run the tests. You can also run `bin/console` for an interactive prompt that will allow you to experiment.

To install this gem onto your local machine, run `bundle exec rake install`. To release a new version, update the version number in `version.rb`, and then run `bundle exec rake release`, which will create a git tag for the version, push git commits and tags, and push the `.gem` file to [rubygems.org](https://rubygems.org).

## Contributing

Bug reports and pull requests are welcome on GitHub at https://github.com/cpankaj/yquotes.


## License

The gem is available as open source under the terms of the [MIT License](http://opensource.org/licenses/MIT).

