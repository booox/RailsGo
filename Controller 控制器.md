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

## 权限控制
- [Rails 应用开发笔记（四）](http://liuzxc.github.io/articles/rails-app-study-04/)

```
  def require_admin
    if not admin?
      flash[:error] = "您没有权限操作！"
      redirect_to home_path
    end
  end
```

> before_action 和 before_filter 的区别 before_action 和 before_filter 其实是一个东西，只是在 Rails4.0 之前使用的是 before_filter，之后改成了 before_action，相当于功能一样，只是名字不同而已。
