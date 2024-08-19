# Mjollnir

Trying to Make Ruby's Parser Available as a Gem.

## Installation

First, install Ruby master with Universal Parser.

```console
RUBY_CONFIGURE_OPTS="cppflags=-DUNIVERSAL_PARSER" rbenv install ruby-dev
```

Clone this repository.

```console
git clone https://github.com/S-H-GAMELINKS/mjollnir.git
```

Move `mjollnir` directory, and run `bundle install`.

```console
cd mjollnir && bundle install
```

And, build Ruby Parser.

```console
bundle exec rake ruby_parser:build
```

Finally, build `Mjollnir` gem  and install it.

```console
bundle exec rake build
gem install pkg/mjollnir-0.1.0.gem
```

## Usage

```ruby
require 'mjollnir/mjollnir'

result = Mjollnir.parse('117 + 117')

p result
# =>
# {
#   "NODE_SCOPE" => {
#     "NODE_OPCALL" => {
#       "recv" => {
#         "NODE_INTEGER" => 117
#       },
#       "mid" => :+,
#       "args" => {
#         "NODE_LIST" => [
#           {
#             "NODE_INTEGER" => 1
#           }
#         ]
#       }
#     }
#   }
# }
```

## Development

After checking out the repo, run `bin/setup` to install dependencies. You can also run `bin/console` for an interactive prompt that will allow you to experiment.

To install this gem onto your local machine, run `bundle exec rake install`. To release a new version, update the version number in `version.rb`, and then run `bundle exec rake release`, which will create a git tag for the version, push git commits and the created tag, and push the `.gem` file to [rubygems.org](https://rubygems.org).

## Contributing

Bug reports and pull requests are welcome on GitHub at https://github.com/[USERNAME]/mjollnir.

## Referenced implementations

[yui-knk/ruby-parser](https://github.com/yui-knk/ruby-parser)

## License

The gem is available as open source under the terms of the [MIT License](https://opensource.org/licenses/MIT).
