---
layout: post
title:      "Solefood - Ruby on Rails Porfolio Project"
date:       2020-06-14 23:17:52 -0400
permalink:  solefood_-_rails_sneaker_collector_app
---



### My rails app Solefood is a sneaker collector sytems management app. App allows user to create an account with password, add sneakers with  a brand association with full CRUD functionality, comment on other user sneakers & lastly delete their own account.

### Below are some of the nuts & bolds upon which this app was built.


### The Rails project explores the conventions of MVC, Validations, Authorization, CRUD & Restful Routes.



### MVC Represents a concept Model, Views, Controls in which our framework is structured in a manner that separates concerns.



### Validations such as `has_secure_password` from Active Record are used to protect database from bad data.

...

### OmniAuth - Facebook allows a user to login via facebook rather than creating an new account.

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





















