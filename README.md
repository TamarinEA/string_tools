# StringTools

Here comes some string tools we often use in Abak-Press. We divided them in two groups. Some of them are class methods of StringTools class and others are extend base String class

## Installation

Add this line to your application's Gemfile:

```ruby
gem 'string_tools'
```

And then execute:

    $ bundle

Or install it yourself as:

    $ gem install string_tools

## Usage

TODO: Write usage instructions here

### Transliteration

Usage: ```StringTools.transliteration_variations(<string>)```.
Method returns an Array of Strings. Returned strings are: given string, string in different keboard layout and transliteration of whichever of first two string happens to be in Russian.
If there is a char in strng which isn't a part of RU <-> EN keyboard mapping, or string containes both Russian and English chars, only given string wrapped in Array is returned.
Examples:
```ruby
StringTools.transliteration_variations('"Мы почитаем всех нулями, А единицами — себя." - А. С. Пушкин')
=> ["\"Мы почитаем всех нулями, А единицами — себя.\" - А. С. Пушкин",
  "@Vs gjxbnftv dct[ yekzvb? F tlbybwfvb — ct,z/@ - F/ C/ Geirby",
  "\"My` pochitaem vsex nulyami, A ediniczami — sebya.\" - A. S. Pushkin"]
```
```ruby
StringTools.transliteration_variations('Ntrcn d ytdthyjq hfcrkflrt')
=> ["Ntrcn d ytdthyjq hfcrkflrt", "Текст в неверной раскладке", "Tekst v nevernoj raskladke"]
```
```ruby
StringTools.transliteration_variations('Еуче шт цкщтп лунищфкв дфнщгею')
=> ["Еуче шт цкщтп лунищфкв дфнщгею", "Text in wrong keyboard layout.", "Euche sht czkshhtp lunishhfkv dfns    hhge."]
```
```ruby
StringTools.transliteration_variations('ﻮﻴﻜﻴﺒﻳﺪﻳ')
=> ["ﻮﻴﻜﻴﺒﻳﺪﻳ"]
```

## Development

After checking out the repo, run `bundle install` to install dependencies. Then, run `bin/console` for an interactive prompt that will allow you to experiment.
To install this gem onto your local machine, run `bundle exec rake install`. To release a new version, update the version number in `version.rb`, and then run `bundle exec rake release` to create a git tag for the version, push git commits and tags, and push the `.gem` file to [rubygems.org](https://rubygems.org).

## Contributing

1. Fork it ( https://github.com/abak-press/string_tools/fork )
2. Create your feature branch (`git checkout -b my-new-feature`)
3. Commit your changes (`git commit -am 'Add some feature'`)
4. Push to the branch (`git push origin my-new-feature`)
5. Create a new Pull Request
