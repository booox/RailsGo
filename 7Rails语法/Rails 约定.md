# 约定

## 命名
````
类名采用--驼峰式
文件名采用--蛇底式
```

## 空格
```
{ "first_name" => "Michael", "last_name" => "Hartl"  }  # 花括号左右加入空格
```

## 括号
Ruby 中，括号可以省略
```
# Parentheses on function calls are optional.
stylesheet_link_tag("application", media: "all",
                                   "data-turbolinks-track" => true)
stylesheet_link_tag "application", media: "all",
                              "data-turbolinks-track" => true
```
- 如果Hash是最后一个参数，它的花括号也是可以省略的
```
# Curly braces on final hash arguments are optional.
stylesheet_link_tag "application", { media: "all",
                                     "data-turbolinks-track" => true }
stylesheet_link_tag "application", media: "all",
                                   "data-turbolinks-track" => true
```

## 代码长度
每行代码不要超过 80 列。
