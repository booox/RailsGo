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

##  JSON
```
JSON["calendars"].each do |key, value|
  # working with value["busy"]...
end
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

## 判断非空
- `present?` 可判断 [],{},"",都为空
- `nil?`
- `blank?`


## SCSS文件中使用 assets
```
.right-bar-filler{
    background:url(asset-path('right_bar_filler.jpg', image)) repeat-y;
    padding-top:0px;}
```

## string
- 转换为 symble
  ```
  # 语法
  str.intern => symbol
  str.to_sym => symbol

  # 例子
  "Koala".intern         #=> :Koala
  s = 'cat'.to_sym       #=> :cat
  s == :cat              #=> true
  s = '@cat'.to_sym      #=> :@cat
  s == :@cat             #=> true
  ```
- 处理空格
```
# 去除两端空格
"   I have leading and trailing white space   ".strip

# 取出行内空格
"I have white space".delete(' ')

# regex 去除空格换行等
"   I have leading and trailing white space   ".gsub(/\s+/, "")
```
