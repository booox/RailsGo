# AJAX
```

unless items.nil?
  render json: {status: 'failed', alert: '查询数据为空'} and return
end

render json: {status: 'success', value: items}
```