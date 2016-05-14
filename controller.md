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
