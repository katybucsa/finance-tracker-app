Add Bootstrap 5 to Rails 7 app (sass)
1. Rename `app/assets/stylesheets/application.css` to `app/assets/stylesheets/application.sass` and add the following line:
    ```sass
    @import 'bootstrap'
    ```
2. Add the following lines in `app/javascript/application.js`:
    ```javascript
    import 'popper'
    import 'bootstrap'
    ```
   
3. Add the following lines in `config/importmap.rb`:
    ```ruby
    pin 'popper', to: 'popper.js', preload: true
    pin 'bootstrap', to: 'bootstrap.min.js', preload: true
    ```

4. Add the following line in `config/initializers/assets.rb`:
    ```ruby
    Rails.application.config.assets.precompile += %w( bootstrap.min.js popper.js)
    ```

5. Run the following commands:
    ```
    bundle install
    rails assets:precompile
    ```
