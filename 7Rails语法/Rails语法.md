# 七、Rails语法

## Time
- [api-day](http://stevenyue.com/blogs/date-time-datetime-in-ruby-and-rails/)
```
# time TO 2016-06-04
Time.at(@romantic_order.consume_time + 1.day - Time.now).utc.strftime("%H:%M:%S")
```

## 循环语句
- if
    ```
    if true

    elsif

    end
    ```

- `case`
    ```
    case name
      when "John"
        puts "Howdy John!"
      when "Ryan"
        puts "Whatz up Ryan!"
      else
        puts "Hi #{name}!"
    end
    ```

- `真假`
    ```
    只有false和nil是假，其他都为真
    ```

## Array

```
# 将 nil 对象踢出！！！！
Array.wrap([nil])
# 带 index 的遍历
  def count(array, status)
    array.select{|i| i.status == status}.length
  end
```

## array
```
@suggested_horses.include?(horse)
```

## date
```
# 获得今天星期几
Time.now.wday

# 日期转换
Time.now.strftime("%Y-%m-%d %H:%M:%S")  #2016-05-23 14:32:32

# 字符串 to Time
return "2016-01-01".to_time

# 获得本周开始日期
Date.today.beginning_of_week

# 获得本周开始时间
Time.now.beginning_of_week

# 获得今天开始
Time.now.beginning_of_day
```
