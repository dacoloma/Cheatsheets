# Rails 
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
eyJoaXN0b3J5IjpbLTE5OTAwMDExNiwtNDA3ODE3OTM2LC0yMD
g4NzQ2NjEyLDczMDk5ODExNl19
-->