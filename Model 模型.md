# Module

## 新建
```
# 生成 vote 表，并建立一列
rails generate model vote topic_id:integer
# 写入数据库
rake db:migrate

# 建立 Model: post，同时生成
# post 的二個欄位: content(text 文字屬性) 跟 group_id (integer 整數屬性)0
rails g model post content:text group_id:integer
rake db:migrate
```

## 查询

- rails console 控制台查询
```
rails c  # 命令行中进入控制台
first_user = User.first  # 查询第一个用户资料
first_user.microposts  # 查询关联表
```

- 设定 scope 查询，提高复用
```
class Product < ActiveRecord::Base
  scope :active, -> { where state: 'active' }
  scope :inactive, -> { where state: 'inactive' }
end
```


