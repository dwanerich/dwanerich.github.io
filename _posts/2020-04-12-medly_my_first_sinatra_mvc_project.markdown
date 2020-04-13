---
layout: post
title:      "MedLy - My First Sinatra Application"
date:       2020-04-12 15:16:32 -0400
permalink:  medly_my_first_sinatra_mvc_project
---


Welcome to the technical journey of my Sinatra MVC project named MedLy! (that i am super proud of by the way ; )

MedLy is an application that allows users to create an account for medication adminstration reminders. Features include  creating, viewing, editing, and deleting medications and their interval of administration value. 

See detail and concepts below for which this app was build. I found that building this project was best executed by breaking it down into several parts and putting it all back together.

Special thanks to Corneal Gem!! A Sinatra Project Template (courtesy of Flatiron Alumni). With Corneal installed and a new project created, you're off to the races...


**the project required a minimum of two model classes, for my particular app these classes would be:**

#### 1. `User`
#### 2. `Medicine`

### `Class User < ActiveRecord::Base` 
### `end`


>  with a relationship of:
>  
>  :`has_many` && `:belongs_to`  where Medicine :belongs_to User && User :has_many medicines right?  
 
### `:MVC=> {'Models','Views', 'Controllers'}`

> MVC is a concept which stands for Models, Views, Controllers using the analogy of a restaurant Chef, waiter & costumer to best describe it relationship. MVC also represents a concept we know as separation of concerns.


#### Model = :Chef=> {"Brains Behind"}

#### View = :Customer => {"Visuals what you see"}

#### Controller = :Waiter=> {"Middle man"}

 
###  Active Record
 
>  we create tables for our models via ActiveRecord and migrate data via Rake. 
>  Models are created with their respective corresponding attributes.
>  Our database & Model classes all communicate with information back and forth with controllers that's a small but yet major component of the robust responsive web application.
>  

```
Class CreateUsers < ActiveRecord::Migration
  def change
    create_table :users do |t|
      t.string :name
      t.string :password
      t.string :password_digest

      t.timestamps null: false
    end
```


### `CRUD = ["CREATE", "READ", "UPDATE", "DELETE"]`

CRUD represents our four basic functions of a model . Create. Read. Update. Delete. In our App a user can create a medicine, see their medicine, update & delete.


### `Controllers < Sinatra::Base`

> for MedLy we split our controller into 3. By convention we use a main controller to inherit from Sinatra::Base and the other controllers inherit from the main controller. Note only one controller can be ran at once in our config.ru so others
> must be set to use.

####  `users_controller <applications_controller`
> this is where our post & gets requests for user account created.

#### `medicines_controller < applications_controller`
> this controller is where our medicine CRUD code lives

#### `sessions_controlller <applications_controller`
> here is where we create user login & log out controls.
> sessions is like a cookie but on the server side best described as a hash that stores user data for the time the user is logged into their account. Sessions allows a user to remain logged in once and not have to continue logging in when they navigate the site.

### VALIDATION

> ##### `has_secure_password`
> ##### `validates :password, presence: true`
> in our model class we inherit macros from brypt for security and validation. In our app we used the secure password and unique username as a way to control bad data coming into our base.

### Bonus

###  "The application sends users a reminder text message when

`if (Time.now - medicine.interval.minutes) >= medicine.last_reminder_sent_at
          "sending..."`

At any point when a user is logged in, user can delete their medication or edit name, condition they're taking medication for and the interval. lastly, another user should not be able to edit another user's profile or medications."


### end

