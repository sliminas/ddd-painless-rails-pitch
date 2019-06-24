## DDD / Painless Rails

what we could use to make our code better

---

## Content

@ol

- Semantic model naming
- Controller toplevel namespaces
- Controller namespace per bounded context
- Nested controllers with route

@olend

---

### Semantic naming of models
---
```ruby
class Shop < ActiveRecord
end

class Sale < ActiveRecord
end
```

---
### Semantic naming of models
```ruby
class Shop < ActiveRecord
end

class Sale < ActiveRecord
end
```
```ruby
class Partner::Shop < ActiveRecord
end

class Partner::Sale < ActiveRecord
end
```

---
Controller toplevel namespacing by usecase
api, feeds, web, report
one base controller per namespace
---
Controller namespace per bounded context
Marketing::ProductsController
Warehouse::ProductsController
---
Nested controllers with route

---
# __The End__
