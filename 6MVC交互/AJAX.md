# AJAX
1. 控制器
```
unless items.nil?
  render json: {status: 'failed', alert: '查询数据为空'} and return
end

render json: {status: 'success', value: items}
```

2. 页面


- [Rails 开发：那些年，我们一起踩过的坑](http://talkcool.info/?p=19)

3. 解决了ajax必须刷新才能加载问题
```
# 删除此插件，或者 JS 使用 page_change
//= require turbolinks
```

4. 401 权限限制问题
- 第一种方案
```
# 关闭此 action 的 frogery 功能
protect_from_forgery :except => [:create]
```

- 第二种方案
 [protect_from_forgery & Unobtrusive Javascript](http://stackoverflow.com/questions/731504/protect-from-forgery-unobtrusive-javascript)
```
<script>
  function authToken() {
    return '<%= form_authenticity_token if protect_against_forgery? -%>';
  }


$.ajax({
    type: 'put',
    url:  url,
    data: { foo: bar,
            authenticity_token: authtoken()
          },
    complete: function(data) {}
})
</script>
```


