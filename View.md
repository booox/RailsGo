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

- [由于引用两次ujs导致remote submit twith](http://stackoverflow.com/questions/7411271/form-submitted-twice-due-to-remote-true)

## 文件存放路径
```
app/assets  # 存放当前程序用到的资源文件
lib/assets  # 存放自己开发的代码库用到的资源文件
vendor/assets  # 第三方代码库用到的资源文件
```

## 预处理
foobar.js.erb.coffee  # 按照扩展名从右向左处理
asset pipeline 默认合并压缩 css/js 文件

## SCSS
```
&:hover {  # 引用父标签
  ...
}

Bootstrap 中有颜色变量，以@开头，可直接在 SCSS 中替换$ 使用
```

## navbar
```
<ul class="nav">
  <li class="<%= 'active' if params[:controller] == 'controller1' %>"> <a href="/link">Link</a> </li>
  <li class="<%= 'active' if params[:controller] == 'controller2' %>"> <a href="/link">Link</a> </li>
  <li class="<%= 'active' if params[:controller] == 'controller3' %>"> <a href="/link">Link</a> </li>        
</ul>
```

## button_to
```
:disable_with => "Submitting...."
```
