# views相关

## 概念
ERb: Embedded Ruby （嵌入式 Ruby）

## 使用模板
```
# View 中
<% provide(:title, 'Home') %>

# Layout 中
<title>Ruby on Rails | <%= yield(:title) %></title>

# 为 provide 提供默认值
< title> < %= content_for?(:title) ? content_for(:title) : 'This is a default title' %> < /title>

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

- img_path
```
# 获取文件经过 rails 解析后 url 地址
<%= asset_path("rails.png") %>
```

## Simple_fome_for
```
<%= form_for :romantic_order, url:webapp_romantic_order_path(current_user.id), :html => {id: "cancle"}, method: :patch do |f| %>
    ……
<% end %>

# <!--支付订单-->
<%= simple_form_for :set_menu, method: :post, remote: true,
                    url: webapp_romantic_order_pay_path(params[:id])  do |f| %>
    <%= f.input :to_pay, as: :hidden, input_html: {name: "to_pay", value: true} %>
    <button type＝"submit" style＝"display:none" id= "btn_pay"></button>
<% end %>
```

