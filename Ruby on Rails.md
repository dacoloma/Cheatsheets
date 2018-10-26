# Rails 
## Gemfile
```ruby
source 'https://rubygems.org'

# authentification
gem 'devise'
# gem 'pundit'

gem 'rails'
gem 'puma'
gem 'sass-rails'
gem 'uglifier'
gem 'coffee-rails'
gem 'jquery-rails'
gem 'turbolinks'
gem 'jbuilder'
gem 'bootstrap', '~> 4.1.3'

group :development, :test do
  gem 'sqlite3'
  gem 'byebug',  '9.0.6', platform: :mri
  gem 'rspec-rails'
  gem 'pry-rails'
  gem 'pry-byebug'
  gem 'database_cleaner'
  gem "factory_bot_rails"
  gem 'simplecov'
  gem 'rb-readline'
end

group :development do
  gem "better_errors"
  gem "binding_of_caller"
  gem 'letter_opener'
  gem 'web-console'
  gem 'listen'
  gem 'spring'
  gem 'spring-watcher-listen'
end

group :test do
  gem 'capybara'
  gem 'poltergeist'
  gem 'shoulda-matchers'
end

group :production do
  gem 'pg', '0.20.0'
end

# Windows does not include zoneinfo files, so bundle the tzinfo-data gem
gem 'tzinfo-data', platforms: [:mingw, :mswin, :x64_mingw, :jruby]
```
## Checklist
1. Create a new app
```bash
$ rails new app
```
2. Modify the Gemfile
3. Install new gems via bundle 
```bash
$ bundle install --without production
```
4. Test it locally
```bash
$ rails s
```
5. Create models, views, controllers
```bash
$ rails generate model Name attribute:type ...
$ rails generate controllers pluralName first_view second_view ...
```
6. Modify routes.rb
7. Git 
```bash
$ git add file1
$ git commit -m "[NEW] feature"
$ git push origin [branch]
```
8. Database migration
```bash
$ rails db:migrate
```
9. Test it locally
10. Production 
```bash
$ heroku create
$ git push heroku master
$ heroku run rails db:migrate
```
<!--stackedit_data:
eyJoaXN0b3J5IjpbODQ4NTcxMTI5LC0xOTkwMDAxMTYsLTQwNz
gxNzkzNiwtMjA4ODc0NjYxMiw3MzA5OTgxMTZdfQ==
-->