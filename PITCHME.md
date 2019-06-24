## DDD / Painless Rails

What we could use to improve our code

---

## Content

@ol

- Semantic model naming
- Top-level Controller namespaces
- Controller namespace per bounded context
- Nested controllers with route

@olend

---

### Semantic model naming
```ruby
class Shop < ActiveRecord
end

class Sale < ActiveRecord
end
```

---

### Semantic model naming
```ruby
class Partner::Shop < ActiveRecord
end

class Partner::Sale < ActiveRecord
end
```

---

### Semantic model naming

![Logo](assets/img/models.png)

---
### Top-level Controller namespaces based on a way of usage
---

@snap[north-west span-33]
![ApplicationController1](assets/img/app_con1.png)
@snapend
@snap[north span-33]
![ApplicationController1](assets/img/app_con2.png)
@snapend
@snap[north-east span-33]
![ApplicationController1](assets/img/app_con3.png)
@snapend

---

@snap[north-west span-33]
![ApplicationController1](assets/img/app_con4.png)
@snapend
@snap[north span-33]
![ApplicationController1](assets/img/app_con5.png)
@snapend

---
### Top-level Controller namespaces

@ol
- based on a way of usage
- one base controller per namespace
@olend

@ol
- api
- feeds
- web
- report
@olend


---
### Top-level namespaces per bounded context
Marketing::ProductsController
Warehouse::ProductsController
---
### Multiple Nested Controllers

Problem:

@ol
- view for all posts
- view for posts of specific user
@elend

@ol
- `PostsController#index`
- `PostsController#index_all`
- `PostsController#user_index`
@olend

@ol
- `PostsController#index`
- `Users::PostsController#index`
@olend

---
```ruby
resources :posts, only: [:index, :show]
resources :users, only: [:show] do
  scope module: :users do
    resources :posts, only: [:index]
  end
end
```
---

![NestedController1]('assets/img/nested_con1.png')
![NestedController2]('assets/img/nested_con2.png')
---
# __The End__
