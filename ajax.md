# AJAX
1. 控制器
```
unless items.nil?
  render json: {status: 'failed', alert: '查询数据为空'} and return
end

render json: {status: 'success', value: items}
```

2. 页面