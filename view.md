# views相关

## 概念
ERb: Embedded Ruby （嵌入式 Ruby）

## 使用模板
```
# View 中
<% provide(:title, 'Home') %>

# Layout 中
<title>Ruby on Rails | <%= yield(:title) %></title>

# 防止跨站请求伪造
<%= csrf_meta_tags %>
```
## Tips
- 取得数据的三种方式：
```
f[:id]
f.id
f["id"]
```

- button_to 添加参数
```
params: { state: :submitted }
```

## helper
Rails 内置了很多视图方法，也可以自己创建，成为 `helper`

```
# app/helpers/application_helper.rb
module ApplicationHelper  # module 为我们提供了一种把相关方法组织到一起的方式，

  def full_title(page_title)
      base_title = "Ruby on Rails Tutorial Sample App"
      if page_title.empty?
        base_title
      else
        "#{base_title} | #{page_title}"
      end
  end
end
```

- tags
```
# link_to 第一个参数是链接文本，链接地址，[Hash可选]
<%= link_to "sample app", '#', id: "logo" %>

# image_tag 第一个参数为地址，第二可选为 Hash。使用帮助方法，会通过 Asset Pipeline 
# 自动在 app/assets/images/ 中寻找
<%= link_to image_tag("rails.png", alt: "Rails"), 'http://rubyonrails.org/' %>
```

## 引用样式文件
添加文件后需要在 `config/application.rb` 中添加，让 Asset Pipiline 兼容
```
require File.expand_path('../boot', __FILE__)

# 引入 文件 app/assets/stylesheets/custom.css.scss
@import "bootstrap";
```
