---
layout: post
title:      "Solefood - Ruby on Rails Portfolio Project"
date:       2020-06-14 23:17:52 -0400
permalink:  solefood_-_rails_sneaker_collector_app
---


### Solefood is a sytems management app for the sneaker collector. 

### App allows user to create an account with password or login via Facebook, add sneakers with attributes of size, price & brand association with full CRUD functionality. 

### Users can comment on one other's sneakers & lastly delete their own account at will.

### Below are some of the nuts & bolds upon which this app was built.


### The Rails project explores the conventions of MVC, Validations, Authorization, Restful & Nested Routes.


> ### MVC Represents a concept of Model, Views, Controllers in which our framework is structured with distinct separation of concerns.


### Validations such as `has_secure_password` from Active Record are used to protect database from bad data.

### OmniAuth - a middleware in this app we used Facebook user authentication as an alternative for a user login.

```
> Rails.application.config.middleware.use OmniAuth::Builder do
  provider :facebook, ENV['FACEBOOK_KEY'], ENV['FACEBOOK_SECRET']
end
```


### Nested Routes


```
def index
        
        if params[:brand_id]
            @brand = Brand.find(params[:brand_id])
            @sneakers = @brand.sneakers
        else
            @sneakers = Sneaker.all
        end
```


### Many to Many Relationships 

A sneaker belongs to a user, a sneaker belongs to a brand. a user has many brands thru sneakers and a brand has many users thru sneakers.

```
class Brand < ApplicationRecord
    has_many :sneakers
    has_many :users, through: :sneakers

    validates :name, presence: true, uniqueness: true
    scope :alphabetize, -> {order(name: :asc)}
```

`<% end %>`

