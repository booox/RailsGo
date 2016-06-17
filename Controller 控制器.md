# Controller

## redirect_to
```
redirect_to controller: "merchants",action: "show", notice: "餐厅信息更新成功！"
redirect_to :back, notice: "恭喜您，删除成功！"
```

## 命令
```
# 生成控制器，指定两个 Action
rails generate controller StaticPages home help --no-test-framework

# 撤销生成
rails destroy  controller FooBars baz quux
```

## 获得数据
- 从关链表中取出数据
```
def show
    @group = Group.find(params[:id])
    @posts = @group.posts
end
```

## 写入数据库
- `build(app)` = `new(app)` # 别名？


## 更新某属性
```
 user.update_attribute :admin, true
```
