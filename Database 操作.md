# DataBase
```
# 数据库迁移
rake db:migrate

# 撤销迁移
rake db:rollback

# 回滚到任意版本
rake db:migrate VERSION=0
```

## 数据库操作
```
rails generate model User name:string email:string  # 生成数据库使用 模型User 单数

# 模型表现的单个用户特征，而表储存了多个数据，用复数

rails console --sandbox  # rails c 中的沙盒模型，退出后不保存结果

 User.create(name: "A Nother", email: "another@example.org")

 User.find_by(email: "mhartl@example.com")  # 4.0 开始，推荐使用 find_by 查询属性记录

 user.reload.email  # 重新加载对象
```

- update
```
# 直接属性赋值
user.email = "foo@bar.com"

# update_attributes
user.update_attributes(name: "The Dude", email: "dude@abides.org")  # 接收一个 Hash
```

## 拼接结果
```
# author: bobo
module MerchantHelper

  # 按名称和地址搜索商户
  def search_by_name_address(name, address, page)
    p name.to_s + '--------'
    datas = []
    unless name.nil? && address.nil?
      page = page ? page.to_i : 1
      merchants_res = Merchant.where("name LIKE ? AND address LIKE ?", "%#{name}%", "%#{address}%").paginate(page:page,per_page:10)
      merchants_res.each do |f|
        count = f.restaurants.length
        merchant_res = f.as_json
        merchant_res["count"] = count
        datas.push(merchant_res)
      end
    end
    return datas
  end

end
```
