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

