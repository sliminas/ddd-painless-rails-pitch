## DDD / Painless Rails

what we could use to make our code better

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
@snap[north-west span-20]
![ApplicationController1](assets/img/app_con1.png)
@snapend
@snap[north-west span-20]
![ApplicationController1](assets/img/app_con2.png)
@snapend
@snap[north-west span-20]
![ApplicationController1](assets/img/app_con3.png)
@snapend
@snap[north-west span-20]
![ApplicationController1](assets/img/app_con4.png)
@snapend
@snap[north-west span-20]
![ApplicationController1](assets/img/app_con5.png)
@snapend

---
api, feeds, web, report
one base controller per namespace
---
### Top-level namespaces based on a way of usage
Marketing::ProductsController
Warehouse::ProductsController
---
### Nested controllers with route

---
# __The End__
