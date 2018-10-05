# CSS
## Process changement de CSS pour une page donnée

- **Créer un fichier SCSS**
  * Contenu personnalisé pour une page donnée
- **Se rendre sur Application.html.erb**
  * Ajouter dans le head (après les meta)
```
<%= stylesheet_link_tag    ‘application’, media: ‘all’, ‘data-turbolinks-track’: ‘reload’ %>
<%= stylesheet_link_tag  yield(:stylesheets) , media: ‘all’, ‘data-turbolinks-track’: ‘reload’ %>
```
- **Se rendre dans Application.css**
  * Ajouter cette ligne en dernier require
```
*= stub nom_du_scss
```
- **Se rendre dans config/initializer/asset.rb***
  * Ajouter en dernière ligne
```
Rails.application.config.assets.precompile += %w( nom_du_scss.scss)
```
- **Se rendre sur la fichier html.erb à personnaliser**
  * Ajouter en première ligne
```
<% provide(:stylesheets, 'nom_du_scss') %>
```  

<!--stackedit_data:
eyJoaXN0b3J5IjpbNjYxOTE3MDk5XX0=
-->