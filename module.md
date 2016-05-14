# Module
设定常用查询条件，方便复用
```
class Product < ActiveRecord::Base
  scope :active, -> { where state: 'active' }
  scope :inactive, -> { where state: 'inactive' }
end
```

## rails console 查询
```
first_user = User.first  # 查询第一个用户资料
first_user.microposts  # 查询关联表
```
