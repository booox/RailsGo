# Rails_常用命令

## Model

- 为表添加一列
```
rails g migration add_image_to_paintings image:string
rails d .... # 删除上个命令生成文件
```

## Controller
```
# 生成控制器，指定两个 Action
rails generate controller StaticPages home help --no-test-framework

# 撤销生成
rails destroy  controller FooBars baz quux

# 生成 Restful Controller
rails generate controller webapp/resumes index create new destroy show
```
