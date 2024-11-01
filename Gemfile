source "https://rubygems.org"

gem "rails", "~> 7.2.2"
gem "sqlite3", ">= 1.4"
gem "puma", ">= 5.0"
gem "tzinfo-data", platforms: %i[ windows jruby ]
gem "bootsnap", require: false
group :development, :test do
  gem "debug", platforms: %i[ mri windows ], require: "debug/prelude"
  gem "rspec-rails"
  gem "brakeman", require: false
  gem "rubocop-rails-omakase", require: false
end

group :test do
  gem "factory_bot_rails"
  gem "shoulda-matchers"
  gem "faker"
  gem "database_cleaner"
end