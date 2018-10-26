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

#### ATOM
### Faire persister les icones en production
    config/environments/production.rb
    Ajouter ces 2 lignes:
```config.serve_static_assets = true
config.assets.compile = true
```

### Faire persister la background image en production
    Dans le CSS (body)
```background: asset-data-url('background.jpg')
```


## PROCESS UTILISATION DEVISE

### Intégration de Devise
#### TERMINAL
```rails g devise:install
```
    Suivre les indications
    1) Mailer : si voulu
    2) La root : OK
    3) Intégration du gestionnaire d'affichage des msg flash
        app/views/layouts/application.html.erb
            Copier les 2 lignes dans le body, avant le yield
```ruby
<p class="notice"><%= notice %></p>
<p class="alert"><%= alert %></p>
```

### Générer un model pour les Users
#### TERMINAL
```rails g devise User
```
Ce qui se passe automatiquement:
    --> Création de tous les fichiers nécessaires
    --> Initialisation des Routes

#### TERMINAL
```rails db:migrate
```

## Possibilité de modification des views pour les sessions / gestion users
```rails g devise:views```

## génerer le controller de devise si on en a besoin
```rails generate devise:controllers users```

## rediriger les routes pour les controllers qu'on a besoin de customiser
## exemple : si on a besoin de personnaliser le controller session, on ajoute sa route

``` 	devise_for :users, controllers: {
    sessions: 'users/sessions'
    registrations: 'users/registrations'
  }```


##Devise User

```rails generate devise Admin```

##Configure your Admin model

```ruby
class Admin < ActiveRecord::Base
  devise :database_authenticatable, :trackable, :timeoutable, :lockable 
end
```


```ruby
class DeviseCreateAdministrators < ActiveRecord::Migration[5.1]
  def self.up
    create_table :administrators do |t|
      ## Database authenticatable
      t.string :email,              null: false, default: ""
      t.string :encrypted_password, null: false, default: ""

      ## Recoverable
      t.string   :reset_password_token
      t.datetime :reset_password_sent_at

      ## Rememberable
      t.datetime :remember_created_at

      ## Trackable
      t.integer  :sign_in_count, default: 0
      t.datetime :current_sign_in_at
      t.datetime :last_sign_in_at
      t.string   :current_sign_in_ip
      t.string   :last_sign_in_ip

      ## Confirmable
      # t.string   :confirmation_token
      # t.datetime :confirmed_at
      # t.datetime :confirmation_sent_at
      # t.string   :unconfirmed_email # Only if using reconfirmable

      ## Lockable
      # t.integer  :failed_attempts, default: 0, null: false # Only if lock strategy is :failed_attempts
      t.integer  :failed_attempts, default: 0
      t.string   :unlock_token # Only if unlock strategy is :email or :both
      t.datetime :locked_at


      # t.timestamps null: false
      t.timestamps
    end

    #by Yann# add_index :administrators, :email,                unique: true
    #by Yann# add_index :administrators, :reset_password_token, unique: true
    # add_index :administrators, :confirmation_token,   unique: true
    # add_index :administrators, :unlock_token,         unique: true
  end

  def self.down
    drop_table :administrators
  end

end ```

## on migre les tables crées pour devise 

```
rails db:migrate
```

## suite du tutoriel
https://github.com/plataformatec/devise/wiki/How-to-Setup-Multiple-Devise-User-Models

##ajout des scopped views

# config/initializers/devise.rb
config.scoped_views = true

``` rails g devise:views administrators ```

## Ajouter le controller de administrators
```rails generate devise:controllers administrators```

## Ajouter les routes pour les controlleurs que l'on veut personnaliser
```ruby
  devise_for :administrators, controllers: {
    sessions:  "administrators/sessions"
    registrations: "administrators/registrations"
  } ```

## Ajouter dans les views home index 
```html
<%if user_signed_in? %>
	<%= button_to "Log out User", destroy_user_session_path, method: :delete, form_class:"nav-link w-nav-link" %>
<% elsif administrator_signed_in? %>
	<%= button_to "Log out admin", destroy_administrator_session_path, method: :delete, class:"nav-link w-nav-link" %>
<% else %>
	<%= link_to "Inscription utilisateur", new_user_registration_path, class:"nav-link w-nav-link" %>
	<%= link_to "Connexion utilisateur", new_user_session_path, class:"nav-link w-nav-link" %>
	<%= link_to "Connexion administrateur", new_administrator_session_path, class:"nav-link w-nav-link" %>
<% end %>
```

## On crée un administrateur en console
```rails c```

```
[1] pry(main)> a = Administrator.new
=> #<Administrator id: nil, email: "", created_at: nil, updated_at: nil>
[2] pry(main)> a.email = "admin@grools.fr"
=> "admin@grools.fr"
[3] pry(main)> a.password = "123456"
=> "123456"
[4] pry(main)> a.save
   (0.2ms)  begin transaction
  SQL (0.4ms)  INSERT INTO "administrators" ("email", "encrypted_password", "created_at", "updated_at") VALUES (?, ?, ?, ?)  [["email", "admin@grools.fr"], ["encrypted_password", "$2a$11$6NriiugsJIaueVzXej/PE.QJ.wj0Bj3r3oHSbi7I1nJvmYs58r7RG"], ["created_at", "2018-03-12 16:17:19.815668"], ["updated_at", "2018-03-12 16:17:19.815668"]]
   (7.6ms)  commit transaction
=> true
```

https://github.com/plataformatec/devise/wiki/How-to-Setup-Multiple-Devise-User-Models

## on crée un fichier accessible.rb dans app/controllers/concerns
# ../controllers/concerns/accessible.rb
```ruby
module Accessible
  extend ActiveSupport::Concern
  included do
    before_action :check_user
  end

  protected
  def check_user
    if current_admin
      flash.clear
      # if you have rails_admin. You can redirect anywhere really
      redirect_to(rails_admin.dashboard_path) && return
    elsif current_user
      flash.clear
      # The authenticated root path can be defined in your routes.rb in: devise_scope :user do...
      redirect_to(authenticated_user_root_path) && return
    end
  end
end
```

##refaire nos routes aux propre 
```ruby
  devise_for :administrators, path:'admin', controllers: {
    sessions:  "administrators/sessions",
    registrations: "administrators/registrations"
  }
	#routes du controller Devise
 	#ajouter les routes des controlleurs qu'on souhaite customiser
	devise_for :users, path:'', controllers: {
    sessions: 'users/sessions',
    registrations: 'users/registrations'
  }
```
<!--stackedit_data:
eyJoaXN0b3J5IjpbMzg1NzQxNTI5LDIwNTU2OTk0ODgsODQ4NT
cxMTI5LC0xOTkwMDAxMTYsLTQwNzgxNzkzNiwtMjA4ODc0NjYx
Miw3MzA5OTgxMTZdfQ==
-->