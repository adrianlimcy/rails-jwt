# README

This is a simple app following the tutorial found in:
https://medium.com/binar-academy/rails-api-jwt-authentication-a04503ea3248

1.  rails new rails-jwt
2.  add gems
    # Use Json Web Token (JWT) for token based authentication
    gem 'jwt', '~> 1.5', '>= 1.5.4'
    # Use ActiveModel has_secure_password
    gem 'bcrypt', '~> 3.1.7'
3.  bundle
4.  update routes
    # config/routes.rb
    Rails.application.routes.draw do
    resources :users, param: :_username
    post '/auth/login', to: 'authentication#login'
    get '/*a', to: 'application#not_found'
    end
5.  mkdir app/lib
6.  touch app/lib/json_web_token.rb
7.  create json_web_token.rb code
8.  create application_controller.rb codes
9.  rails g model user name:string username:string email:string password_digest:string
10. add user validations in user model
11. rails g controller users
12. add crud to user controller
13. rails g controller authentication
14. implement login features in authentication controller
15. rails db:migrate
